# AI Agent Compliance

Contoh pendukung tesis tentang compliance risk assessment untuk AI agent berbasis LLM.
Evidence diambil dari documentation, code, dan log agent, lalu disatukan dengan rule dari
beberapa framework (EU AI Act, IMDA, dan lainnya) dalam satu knowledge graph.

Semua agent dan datanya fiktif.

| Isi | Link |
|---|---|
| Visualizer KG agent kredit | https://alifbintang1.github.io/ai-agent-compliance/kg-agent-kredit/ |
| Ontology v0 (Turtle) | [kg-agent-kredit/ontology_v0.ttl](kg-agent-kredit/ontology_v0.ttl) |
| KG agent kredit (TriG, 8 named graph) | [kg-agent-kredit/agent_kredit_kg.trig](kg-agent-kredit/agent_kredit_kg.trig) |
| Competency questions (SPARQL) | [kg-agent-kredit/cq/](kg-agent-kredit/cq/) |
| Gambar skenario latar belakang | [gambar/skenario-latar-belakang.png](gambar/skenario-latar-belakang.png) |

Competency questions bisa dijalankan dengan rdflib:

```python
import rdflib
ds = rdflib.Dataset(default_union=True)
ds.parse("kg-agent-kredit/agent_kredit_kg.trig", format="trig")
print(list(ds.query(open("kg-agent-kredit/cq/CQ4.rq").read())))
```
