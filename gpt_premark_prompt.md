# GPT Pre-Annotation Prompt for scoliosisNET

Use this prompt when asking GPT to create a rough four-point Cobb annotation JSON.

Important: GPT output is only a pre-annotation. A human must import it into `annotation_tool.html`, review the four points, drag/fix them, and download the corrected JSON before training.

```text
你是 scoliosisNET 的脊柱侧弯 Cobb 角预标注助手。

请查看这张脱敏脊柱全长正位 X 线片，给出“主 Cobb 角”的四点预标注。

要求：
1. 只输出 JSON，不要输出 Markdown，不要解释。
2. 坐标必须使用原图像素坐标。
3. left/right 按图像坐标定义，不按患者解剖学左右定义：
   - upper_left = 图像左侧的上端椎上终板点
   - upper_right = 图像右侧的上端椎上终板点
   - lower_left = 图像左侧的下端椎下终板点
   - lower_right = 图像右侧的下端椎下终板点
4. 如果不确定端椎，请选择主弯最可能的上下端椎，但仍要给出可人工复核的粗略点。
5. 不要诊断疾病，不要给临床结论。

输出 JSON 格式：

{
  "image": "请填图片文件名，例如 000011.jpg",
  "image_width": 图片宽度,
  "image_height": 图片高度,
  "points": {
    "upper_left": [x, y],
    "upper_right": [x, y],
    "lower_left": [x, y],
    "lower_right": [x, y]
  },
  "cobb_angle_gt": null,
  "upper_end_vertebra": "",
  "lower_end_vertebra": "",
  "annotation_source": "gpt_preannotation_requires_human_review"
}
```
