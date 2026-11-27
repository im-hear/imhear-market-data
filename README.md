# imhear-market-data

ImHear의 Python · KIS WebSocket · Kafka · MySQL · Redis 저장소입니다. 담당 범위는 A의 KIS 수집·분봉·급등락·뉴스/공시 증분 수집과 이벤트 발행, B의 소비 계약 검토입니다.

## 계약과 검증

Kafka의 종목 키와 이벤트 시각을 보존하고 MySQL 결과가 커밋된 뒤 소비 위치를 기록한다. 문서 알림과 색인은 독립 Consumer Group으로 전달한다.

인수 검증 기준은 중복·역순·지연 틱의 분봉 집계, Outbox 재발행, 오래된 Redis 갱신 차단, 문서 재수집 중복 제거입니다.

현재 폴더에는 협업 설정이 들어 있습니다. 서비스 코드와 테스트 하네스가 추가되면 이 위치에 설치, 실행, 검사 명령을 기록합니다. 네 저장소를 함께 여는 경우 상위 작업공간의 `docs/architecture/README.md`와 `docs/team-workflow.md`에서 공용 설계와 PR 흐름을 확인할 수 있습니다.

[에이전트 개발 지침](AGENTS.md)
