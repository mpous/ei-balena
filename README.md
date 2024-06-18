# Edge Impulse and balena boilerplate

[Edge Impulse](https://edgeimpulse.com/) impulses can be [deployed](https://docs.edgeimpulse.com/docs/run-inference/docker) as Docker containers. The [balena platform](https://www.balena.io/) makes deploying containers to one or 100,000+ edge devices a breeze, so this demo shows how they can work beautifully together.


## What you'll need

This boilerplate application intended for any x86 or Raspberry Pi - any version of that board should work. The goal of this application is to show how to deploy Edge Impulse needed Docker container in a balena device.

You'll also need a free or paid Edge Impulse account and an impulse that does image detection (sample public impulses for this are available that you can clone)

Finally, a free or paid balenaCloud account which you can sign up for [here](https://dashboard.balena-cloud.com/signup).

Once this works, feel free to check the example of anomaly detection with a USB camera connected to your balena device.


## Getting started

Create a new fleet in your balena account and deploy a Pi 4 device. (See our [Getting Started Guide](https://docs.balena.io/learn/getting-started/raspberrypi3/python/) for more information!)

Clone this repository to your development machine and also install the [balena CLI](https://github.com/balena-io/balena-cli/blob/master/INSTALL.md)

Clone or create an impulse in Edge Impulse that uses image recognition.

On the Edge Impulse `Deployment` screen, enter `Docker` for the "Search deployment options." You'll see instructions for how to run your model as a Docker container. Note the "Container" and "Arguments" which you'll need to add to the Dockerfile in the ei folder of this cloned repo.

Copy the "Container" value to replace the partial example value after the `FROM` in line one of the Dockerfile in the `eim` folder.

Copy the API key (just the part that begins with `ei_`) to the line that starts `ENV API_KEY=` and also to the second string in the `CMD` command in the last line of the Dockerfile.

Deploy the updated code to your balena device(s) [by issuing](https://docs.balena.io/learn/deploy/deployment/) `balena push` in the balena CLI. 


## How it works

Your model (impulse) is automatically downloaded and run by the Edge Impulse container. It exposes an API which another service can use. Check the [docs here](https://docs.edgeimpulse.com/docs/run-inference/docker) of the API exposed.

The Edge Impulse model UI is available on port 80 of your device.

![Edge Impulse UI running on Docker balena](https://github.com/mpous/ei-balena/assets/173156/7951db1b-17e4-4151-af51-bbc78f8c0f32)


## Troubleshooting

If you have any issues feel free to contact us using the [balena forums](https://forums.balena.io).

