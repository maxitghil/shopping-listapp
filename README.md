# 🛒 Shopping List App

간단한 쇼핑 리스트 웹 앱입니다. 별도 백엔드나 빌드 과정 없이 `index.html` 하나로 동작하며, 데이터는 Supabase(Postgres) 데이터베이스에 저장됩니다.

## Features

- 아이템 추가 / 삭제
- 체크박스로 완료 표시
- 완료(체크)된 항목 일괄 삭제
- 남은 항목 수 표시
- Supabase `shopping_items` 테이블에 데이터 저장 (기기/브라우저 상관없이 동기화)

## Usage

`index.html` 파일을 브라우저에서 열기만 하면 바로 사용할 수 있습니다. 별도 설치나 서버 실행이 필요 없습니다.

## Tech Stack

- HTML / CSS / Vanilla JavaScript
- [Supabase](https://supabase.com) (Postgres + `@supabase/supabase-js`)

## Database

`shopping_items` 테이블 스키마:

| column     | type        | default            |
|------------|-------------|--------------------|
| id         | uuid (PK)   | `gen_random_uuid()`|
| text       | text        | -                  |
| checked    | boolean     | `false`            |
| created_at | timestamptz | `now()`            |

Row Level Security가 활성화되어 있으며, `anon` role에 대해 select/insert/update/delete를 모두 허용하는 정책이 적용되어 있습니다.
