# Inferência Universal de Imagens — Detector YOLO11 + ONNX

Aplicação web de detecção de objetos que roda **inteiramente no navegador**, sem backend.

## Como funciona

1. O usuário faz upload de uma imagem.
2. A imagem é redimensionada e normalizada, e enviada para um modelo **YOLO11n** exportado em **ONNX**, executado no navegador via `onnxruntime-web`.
3. O modelo retorna as detecções (classe, confiança e coordenadas da bounding box), treinado nas 80 classes do dataset **COCO**.
4. Os IDs de classe retornados pelo modelo são traduzidos para português usando o arquivo `classes_coco80_pt.txt`.
5. As bounding boxes são desenhadas sobre a imagem, com o nome da classe (em português) e a confiança de cada detecção.

## Arquivos do modelo

- `public/yolo11n.onnx` — modelo YOLO11n exportado do PyTorch/Ultralytics.
- `public/classes_coco80_pt.txt` — mapa `id;nome_em_portugues` das 80 classes do COCO.

Ambos foram gerados a partir do notebook de treinamento/exportação (PyTorch → YOLO11 → ONNX).

## Observação

A tradução dos nomes não altera o que o modelo aprendeu — ele continua reconhecendo exatamente as 80 categorias do COCO; apenas o nome exibido ao usuário é traduzido.
Link da aplicação feita no lovable: https://id-preview--691c53f4-c42d-59e5-9cb4-4b3b59be1ec6.lovable.app/?__lovable_sha=c46f2286
