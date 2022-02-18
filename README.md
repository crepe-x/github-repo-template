# CrepeX repository template

- 공유 workflow 호출기 포함

## 저장소 초기화 후 할일

1. 아래 label setting 적용 명령어를 사용해서 저장소 라벨을 생성
2. `labels.json`, `images`를 삭제

---

## Github Label 세팅

### Label 이란?

- Issue, PR 에 붙여서 분류하기 위한 이름표

### Github 액세스 토큰 발급

[https://github.com/settings/tokens](https://github.com/settings/tokens)

- `Generate new token` 클릭
- 원하는 이름 입력
- `scopes`에서 repo 선택

![](./images/new-personal-access-token.png)

### Label 정의하기

- `labels.json` 파일에 JSON Array 형태로 정의
- `name`, `color`, `description` 을 정의할 수 있음

```json
[
  {
    "name": "status/critical",
    "color": "8c001a",
    "description": "우선순위 긴급"
  }
]
```

### 정의 된 Label 적용하기

- `액세스 토큰`, `계정명`, `저장소 이름`을 자신의 것으로 변경

```sh
npx github-label-sync --access-token [액세스 토큰] --labels labels.json [계정명]/[저장소 이름]
```

### Label 설정 적용 전

![](images/before-apply-labels.png)

### Label 적용 후

![](images/after-apply-labels.png)

# 참고

- [github-label-sync](https://github.com/Financial-Times/github-label-sync)
