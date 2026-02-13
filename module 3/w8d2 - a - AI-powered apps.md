

# AI-powered apps


## Demo: integrating our backend with an LLM 

Example: 
- https://chatgpt.com/share/698f1780-0eb4-8003-af97-4c7a74a6070b

<!-- 
  @todo: 
  - prepare backend for that demo (can skip the frontend and show the demo with Postman)
-->


Some topics to discuss:
- Never expose your API keys to frontend ⚠️
- Prompt engineering and good practices:
   - define the role
   - be explicit
   - constrain output format 
      - e.g. "respond only in valid json", "return an array of objects with these properties..."
   - provide examples of the expected result
      - zero shot vs. one shot vs. few shot
- context
- temperature
- prompt injection
   - one way of mitigating that risk is to use a very strict system prompt
   - another technique would be tu use a guard model (e.g. Run a smaller model to classify: "Is this a prompt injection?")
- error handling
- costs
- latency (AI calls are slow compared to DB queries)

