# LLM CVRP runner

Binario auxiliar utilizado por el TFM para integrar una heurística Rust generada dentro de PlanForge. Registra la función con el nombre `llm_001` y delega la traducción PDDL, la búsqueda, los límites de recursos, los logs y la escritura del plan en la CLI normal de PlanForge.

El pipeline copia temporalmente cada candidato sobre `src/main.rs`, compila el paquete y restaura siempre este archivo base al terminar. La ejecución manual desde la raíz del repositorio es:

```bash
cargo run --release -p planforge-llm-cvrp -- \
  --search 'gbfs(llm_001())' \
  domain.pddl problem.pddl
```

Las evaluaciones automatizadas se lanzan desde el repositorio hermano `mulcia-tfm-hllm-pipeline`; los PDDL proceden de `mulcia-tfm-artifacts`.
