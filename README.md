<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI 랭크 대시보드</title>
  <style>
    /* 대시보드 기본 스타일 */
    body {
      background-color: #111827;
      color: #d1d5db;
      font-family: 'Segoe UI', sans-serif;
      padding: 20px;
    }
    .dashboard-title {
      background-color: #1f2937;
      padding: 20px;
      font-weight: bold;
      font-size: 1.5em;
      margin: 20px 0;
      text-align: center;
      color: white;
      border-radius: 8px;
    }
    .rank-list {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .rank-item {
      background-color: #1f2937;
      padding: 12px 20px;
      border-radius: 12px;
      margin-bottom: 12px;
      width: 80%;
      font-size: 1em;
      display: flex;
      align-items: center;
    }
    /* 1위 강조 스타일 */
    .rank-item.first {
      font-size: 1.8em;
      font-weight: bold;
      justify-content: center;
      width: 100%;
      margin-bottom: 24px;
    }
    /* 2위 이하 스타일 */
    .rank-item:not(.first) {
      font-size: 1em;
      justify-content: flex-start;
    }
  </style>
</head>
<body>
  <div class="dashboard-title">AI 랭크 대시보드</div>
  <div id="rank-list" class="rank-list"></div>

  <script>
    const container = document.getElementById('rank-list');

    // 직접 입력할 AI 모델 목록 (첫 번째는 ChatGPT로 설정)
    const models = [
      { name: 'ChatGPT' },
      { name: '뤼튼 AI' },
      { name: 'Google Gemini' },
      { name: 'DeepL' },
      { name: 'DeepSeek' }
    ];

    // AI 모델 목록 렌더링 함수
    function renderModels(models) {
      container.innerHTML = '';
      if (!Array.isArray(models) || models.length === 0) {
        container.textContent = '등록된 AI 모델이 없습니다.';
        return;
      }
      models.forEach((model, index) => {
        const div = document.createElement('div');
        div.classList.add('rank-item');
        // 1위는 first 클래스 추가
        if (index === 0) div.classList.add('first');
        div.textContent = `${index + 1}. ${model.name}`;
        container.appendChild(div);
      });
    }

    // 페이지 로드 후 바로 렌더링
    document.addEventListener('DOMContentLoaded', () => renderModels(models));
  </script>
</body>
</html>

