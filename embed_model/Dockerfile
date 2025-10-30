FROM dylanturn/runpod-ollama:0.12.7

ENV MODEL_NAMES=mdq100/Gemma3-Instruct-Abliterated:27b,goekdenizguelmez/JOSIEFIED-Qwen3:30b
ADD preload_model.sh /preload_model.sh
RUN apt-get update && apt-get install bash
RUN chmod +x /preload_model.sh && /preload_model.sh

# Copy the model to the volume
FROM dylanturn/runpod-ollama:0.12.7
COPY --from=0 /runpod-volume /runpod-volume
