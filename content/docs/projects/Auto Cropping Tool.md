+++
title = "Auto Cropping Tool"
+++

I take lots of screenshots on my phone, but I'm constantly plagued by black borders around the images. While it's pretty easy to crop off this border manually, it would be nice to have a tool that does it for me.
## Execution

https://github.com/JakeJMattson/PeaceOfCrop

I used [Javalin](https://javalin.io/) to create a simple webserver with a single POST endpoint that accepts an image. The image gets scanned from the center in each direction until the edge is reached, or a black pixel is found. It then scans on the other axis to confirm that it is a line of black and not just some black pixels within an image. Once all the borders are found, the image is cropped and the webserver responds with a Base64 result.

## Usage

On my iPhone I created a shortcut that allows me to select a photo from the Photos app, POST it to my server, decode the Base64 contents, then save the new photo to my phone.