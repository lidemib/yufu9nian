# AI做网站 封面图生成 Prompt

## 文章：AI做网站——用AI年入百万的实操路径

Type: conceptual | Palette: warm | Rendering: flat-vector
Text: title-only | Mood: balanced | Aspect: 16:9

## Prompt (OpenAI gpt-image-2)

A professional article cover image for a Chinese food entrepreneurship blog.
Theme: AI making websites to earn money for restaurant owners.
Design: clean modern flat vector illustration, warm orange-red and cream color scheme.
Visual elements: a stylized computer screen showing a website with dumpling icon, a chef hat icon, and upward growth arrows.
Chinese title placeholder space at top. 16:9 widescreen. WeChat article hero image style.
Minimalist, professional, warm and inviting. No realistic human faces.

## 生成命令 (PowerShell)

$apiKey = $env:OPENAI_API_KEY
$body = @{model="gpt-image-2"; prompt="A professional article cover image for a Chinese food entrepreneurship blog. Theme: AI making websites to earn money for restaurant owners. Design: clean modern flat vector illustration, warm orange-red and cream color scheme. Visual elements: a stylized computer screen showing a website with dumpling icon, a chef hat icon, and upward growth arrows. Chinese title placeholder space at top. 16:9 widescreen. WeChat article hero image style. Minimalist, professional, warm and inviting. No realistic human faces."; size="2048x1152"; quality="medium"; n=1} | ConvertTo-Json
$r = Invoke-RestMethod -Uri "https://api.openai.com/v1/images/generations" -Method POST -Headers @{Authorization="Bearer $apiKey";ContentType="application/json"} -Body $body -TimeoutSec 60
$r.data[0].url
