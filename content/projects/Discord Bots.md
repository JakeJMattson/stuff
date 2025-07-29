## Project

I needed a way to host my personal discord bot projects on my [Server]({{< relref "things/Server" >}}). Unraid runs apps via docker out of the box, so this was the simplest deployment strategy. Since the bots are only personal, I didn't want to push the code anywhere either.
## Execution

Knowing I wanted to use Docker for deployment, [Docker Hub](https://hub.docker.com/) came up as an immediate thought. With the idea of keeping the entire process local, I didn't want to push the image somewhere. I found that instead you can host your own [private registry](https://hub.docker.com/_/registry). This registry communicates over HTTP, which many services don't support by default due to security. This was solved by adding `"insecure-registries": ["192.168.1.123:9362"]` to my Docker Engine config. This is the internal static IP of my server and the port the registry is running on.

To submit my project to the registry, I create a tag and an image which includes the registry information
```
docker build -t 192.168.1.123:9362/project .
docker push 192.168.1.123:9362/project
```

Once the image is on the server, now I have to actually run it. You could do this manually, but what are computers for if you don't automate everything? I found [Watchtower](https://github.com/nicholas-fedor/watchtower) which was able to do exactly what I needed. You can have it poll a registry for new images and have them deployed automatically. Since this is my own personal registry, I can poll it as often as I want with no concern for rate limiting.
## Usage

With fully automated deployment on the server, I only needed to make a script to repeat the tag creation steps as needed. I setup this script to be executed when I press the 'Run' button in IntelliJ. All of that means I can make a code change, press a button, and have it running in about 30 seconds without any input from me.