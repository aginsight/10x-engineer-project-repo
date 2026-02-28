# API Reference — Examples

This companion file provides runnable examples for the PromptLab API.

Base URL: http://127.0.0.1:8000/

## List prompts (search)

```bash
curl -s "http://127.0.0.1:8000/prompts?search=template" | jq
```

## Create a prompt

```bash
curl -s -X POST http://127.0.0.1:8000/prompts \
  -H "Content-Type: application/json" \
  -d '{"title":"Hello","content":"Write a short poem about AI.","description":"Poem generator"}' | jq
```

## Get a prompt

```bash
curl -s http://127.0.0.1:8000/prompts/abcd-1234 | jq
```

## Replace a prompt (PUT)

```bash
curl -s -X PUT http://127.0.0.1:8000/prompts/abcd-1234 \
  -H "Content-Type: application/json" \
  -d '{"title":"Hello v2","content":"Updated content","description":"Updated"}' | jq
```

## Patch a prompt (partial update)

```bash
curl -s -X PATCH http://127.0.0.1:8000/prompts/abcd-1234 \
  -H "Content-Type: application/json" \
  -d '{"description":"Add a tone: humorous"}' | jq
```

## Delete a prompt

```bash
curl -s -X DELETE http://127.0.0.1:8000/prompts/abcd-1234 -I
```

## Collections — create

```bash
curl -s -X POST http://127.0.0.1:8000/collections \
  -H "Content-Type: application/json" \
  -d '{"name":"Poems","description":"Short poem templates"}' | jq
```
