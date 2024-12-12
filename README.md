**This repository has been archived.**

DigitalOcean has acquired Paperspace. We recommend exploring [DigitalOcean GPU Droplets](https://docs.digitalocean.com/products/droplets/how-to/gpu/), DigitalOcean Managed Kubernetes with [GPU Worker Nodes](https://docs.digitalocean.com/products/kubernetes/details/features/#gpu-worker-nodes), or the [DigitalOcean Gen AI Platform](https://docs.digitalocean.com/products/genai-platform/) as robust, fully supported alternatives. These platforms offer comprehensive solutions tailored to modern GPU-based workloads.

# Create an OpenAI API compatible endpoint on Paperspace using open source models.

Here's a relatively easy way to get your own OpenAI compatible API endpoint running on Paperspace.

1. Create a Paperspace account, go to Gradient > Deployments > Create
2. Select a GPU, such as P4000 $0.51/hr (can be started/stopped at any time)
3. For Docker image, you can use `ollama/ollama:latest` - details here: https://github.com/ollama/ollama
4. Ports: 11434
5. Once deployed, you will be given a new https endpoint.
6. Pull a new image such as `llama3` using ```curl https://<yourendpoint>.paperspacegradient.com/api/pull -d '{"name": "llama3"}'```
8. That’s it! you’ve now got an OpenAI compatible API endpoint available at your Gradient URL, it will work with OpenAI compatible tools.

Paperspace deployment config json:

```json
{
  "apiVersion": "v1",
  "image": "ollama/ollama:latest",
  "name": "ollama",
  "enabled": false,
  "resources": {
    "machineType": "RTX4000",
    "replicas": 1,
    "ports": [
      11434
    ]
  }
}
```
