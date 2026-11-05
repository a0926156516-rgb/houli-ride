# 后里騎跡 後視角載具素材 / Rear-view vehicle sprites

所有素材皆為「從後方看」(facesAway: true) 的透明 PNG 精靈圖，詳細規格以 `manifest.json` 為準。
All sprites are rear-view transparent PNG strips (one row each). `manifest.json` is authoritative.

| 類別 category | 檔名 file | 格 cell (frameW×frameH) | 影格 frames |
|---|---|---|---|
| 腳踏車 bike | `bike_{ayan|xiaopan}_{red|blue|green|yellow}.png` | 384×384 ×7 | 0 straight 直行, 1 lean_left 左傾, 2 lean_right 右傾, 3–6 pedal 踩踏 (8 fps) |
| 機車 moto | `moto_{ayan|xiaopan}_{color}.png` | 384×384 ×3 | 0 straight, 1 lean_left, 2 lean_right |
| 跑車 car | `car_{color}.png` | 384×288 ×3 | 0 straight, 1 turn_left, 2 turn_right |
| NPC 機車 | `npc_moto.png` | 256×320 ×3 | 3 color variants 色款 |
| NPC 轎車 sedan | `npc_sedan.png` | 320×256 ×3 | 3 variants |
| NPC 貨車 van | `npc_van.png` | 320×320 ×3 | 3 variants |

- 錨點 anchor: `(frameW/2, frameH-8)` = 後輪著地中心 rear-wheel ground contact. Draw with `drawImage(sheet, i*fw, 0, fw, fh, x-fw/2*s, y-(fh-8)*s, fw*s, fh*s)`.
- 傾斜 lean: ±20°（繞錨點旋轉 rotated about anchor）；車輛轉向 car turn: ±6° + 輕微斜切 shear。
- 顏色 colors: red #e8483b, blue #2f8fe0, green #3fb85a, yellow #f2b630.
- 預覽 previews: `preview.png`, `preview_*.gif`. 原始生成圖 source renders: `src/`.
- 遊戲程式目前仍以程式繪製（`bikeBack()`），尚未載入這些圖檔。The game still draws the rider procedurally; these sprites are not wired in yet.
