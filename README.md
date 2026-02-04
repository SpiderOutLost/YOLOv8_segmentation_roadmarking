# YOLOv8 Segmentation — Road Markings

Проект по сегментации дорожной разметки на изображениях с использованием **YOLOv8 Segmentation** (ultralytics).

Цель проекта — построить и оценить модель сегментации, способную выделять различные типы дорожной разметки на изображениях.

---

##  Task
**Semantic / Instance Segmentation**

- Объект: дорожная разметка
- Формат аннотаций: polygons
- Модель: YOLOv8-seg

---

##  Dataset
- Исходные аннотации: polygon-based (JSON)
- Формат обучения: YOLO segmentation
- Разделение:
  - Train
  - Validation
- Датасет не публикуется (используется локально)

Классы задаются в `data.yaml`.

---

##  Model
- Architecture: **YOLOv8n-seg**
- Framework: `ultralytics`
- Image size: `640`
- Task: `segment`

---

##  Training
Обучение и валидация выполняются через Python API ultralytics:

```python
from ultralytics import YOLO

model = YOLO("yolov8n-seg.pt")
model.train(data="data.yaml", epochs=50, imgsz=640)
