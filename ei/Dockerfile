# Use the specified base image
# Replace with your container address after FROM

FROM public.ecr.aws/g7a8t7v6/inference-container:49ef46c7e9f063a4aabb5a680c74cc7d60c9d8f7

# Expose port 1337 on the container to the host is standard for the Edge Impulse Docker container, we will change this to 80
EXPOSE 80

# Start the inference server when the container launches
# Set your API key in the second position in the command below
CMD ["--api-key", "<your API key>", "--run-http-server", "80"]
