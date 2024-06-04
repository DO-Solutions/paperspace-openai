# Create an OpenAI API compatible endpoint on Paperspace using open source models.

Here's a relatively easy way to get your own OpenAI compatible API endpoint running on Paperspace.

1. Create a Paperspace account, go to Gradient > Deployments > Create
2. Select a GPU, such as P4000 $0.51/hr (can be started/stopped at any time)
3. For Docker image, you can use `ollama/ollama:latest` - details here: https://github.com/ollama/ollama
4. Ports: 11434
5. Once deployed, you will be given a new https endpoint.
6. Pull a new image such as `llama3` using ```curl https://<yourendpoint>.paperspacegradient.com/api/pull -d '{"name": "llama3"}'```
8. That’s it! you’ve now got an OpenAI compatible API endpoint available at your Gradient URL, it will work with OpenAI compatible tools.
