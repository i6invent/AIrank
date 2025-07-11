<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>AI 랭킹 대시보드</title>
  <style>
    body {
      background-color: #111827;
      color: #d1d5db;
      font-family: 'Segoe UI', sans-serif;
      padding: 20px;
    }
    h1 {
      font-size: 2em;
      border-bottom: 1px solid #ccc;
      color: #93c5fd;
    }
    .dashboard-title {
      background-color: #1f2937;
      padding: 20px;
      font-weight: bold;
      font-size: 1.5em;
      margin: 20px 0;
      text-align: center;
      color: white;
    }
    .rank-item {
      background-color: #1f2937;
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 15px;
    }
    .rank-item strong {
      color: #60a5fa;
      font-size: 1.1em;
    }
  </style>
</head>
<body>
  <h1>AIrank</h1>

  <div class="dashboard-title">AI 랭킹 대시보드</div>

  <div id="ai-list">
    <!-- AI 랭킹 항목들이 여기에 들어갈 예정 -->
  </div>

  <script>
    // 2단계에서 설명
  </script>
</body>
</html>
<script>
  const aiModels = [
    {
      rank: 1,
      name: "GPT-4o",
      description: "OpenAI의 최신 멀티모달 모델. 실시간 사용량 최상위권."
    },
    {
      rank: 2,
      name: "Claude 3 Opus",
      description: "Anthropic의 대규모 언어 모델. 맥락 유지력 우수."
    },
    {
      rank: 3,
      name: "Gemini 1.5 Pro",
      description: "Google DeepMind의 강력한 생성 AI 모델."
    },
    {
      rank: 4,
      name: "Mistral Large",
      description: "유럽계 오픈소스 기반 고성능 언어 모델."
    }
  ];

  const aiListDiv = document.getElementById("ai-list");

  aiModels.forEach(model => {
    const div = document.createElement("div");
    div.className = "rank-item";
    div.innerHTML = `<strong>${model.rank}위: ${model.name}</strong><br>${model.description}`;
    aiListDiv.appendChild(div);
  });
</script>
