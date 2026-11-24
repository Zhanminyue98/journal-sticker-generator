# 提示词配方

以下英文模板来自实际贴纸生成流程。替换 `{SUBJECT}` 为具体主体与姿态；中文用于规划和命名，英文模板用于保持描述一致，这不是工具语言限制。不要仅用“可爱贴纸”概括主题。

## 1. 无参考图的起始素材

```text
Use case: stylized-concept. Asset type: individual premium digital journal sticker. Subject: {SUBJECT}. Soft hand-painted gouache and watercolor on textured paper, refined Japanese stationery aesthetic, gentle muted natural colors. ONE cohesive sticker centered and filling about 85% of frame with a narrow ivory die-cut border. True transparent background outside sticker, no background paper or scene, no cast shadow, no text, no watermark, no extra isolated objects. High quality raster artwork, clean silhouette.
```

示例主体：`one delicate curved fern frond, sage green botanical watercolor`。

## 2. 已有画风的系列扩充

必须同时传入风格参考图，否则删去附图措辞并使用起始模板。

```text
Use case: stylized-concept. Create ONE NEW individual digital scrapbook sticker depicting {SUBJECT}. The attached image is STYLE REFERENCE ONLY, not the subject to copy. Match its delicate watercolor and gouache pigment, visible paper grain, soft muted colors, refined handmade stationery feeling and narrow warm ivory die-cut outline. One cohesive isolated sticker, front-facing where applicable, complete silhouette centered with 8% transparent safety margin on every side. Background genuinely transparent with clean alpha, including holes. No rectangle background unless the subject itself is a paper scrap. No shadow, glow, text, letters, watermark, mockup or multiple sticker sheet. Fine detail readable at small sticker size.
```

已使用的主体示例：

- 自然：`a curved eucalyptus branch with rounded dusty sage leaves`
- 美食：`one ivory ceramic cup and saucer of latte with simple leaf latte art`
- 基础元素：`one torn rectangular ivory paper scrap with small sage green polka dots`

## 3. 可爱动物

原始动物批次使用蕨叶图作为质感锚点。换其他参考图时，将 `do not include fern leaves` 改为适合该参考图的排除描述。

```text
Use case: stylized-concept. Create ONE adorable individual digital scrapbook animal sticker: {SUBJECT}. The attached image is STYLE REFERENCE ONLY for watercolor paper texture, gentle muted colors and warm ivory die-cut border; do not include fern leaves. Cute illustrated proportions: softly rounded body, slightly oversized head, friendly gentle eyes, delicate tiny nose, believable species-specific markings. Refined hand-painted watercolor and gouache on textured paper, charming stationery illustration, no 3D rendering or photorealism. One complete cohesive animal centered with 8% transparent safety margin, no cropping of ears paws or tail. True transparent background, narrow ivory outline, no background scene, shadow, glow, text, letters, watermark or sticker sheet. Anatomically coherent, exactly two eyes, correct number of limbs, no human hands or clothing.
```

已使用的主体示例：`a round baby otter sitting and holding a small smooth pebble, soft brown fur and pale cheeks`。

眼睛与肢体约束要适应构图：闭眼睡觉、侧脸遮挡时，不必强行画出两只可见眼睛；昆虫也不能套用四足动物肢体约束。原始提示词库保留实际调用内容，新的调用以主题合理性为准。

## 4. 失败时的局部修正

- 轮廓被切断：增加完整主体与外边距描述，缩小主体占比。
- 误画为整套展示：强调 `exactly one standalone sticker, no sticker sheet, no layout`。
- 纸纹变成整张背景：强调 `paper texture only inside the subject; outside the cutline is transparent`，同时检查透明背景工具参数。
- 参考内容混入：明确新主体，排除参考图主体；不要只写“照这个再来一张”。
- 系列画风漂移：使用同一已认可锚点，减少无关风格形容词，不反复用上一张新图作参考造成逐步漂移。

这类修正是后续复用建议，并不表示原批次每项都出现过问题。参数应按实际工具接口填写，不假设存在 seed、尺寸或质量等未提供的选项。
