# prisma のクイックスタートの写経
https://www.prisma.io/docs/getting-started/quickstart

## プロジェクト作成
mkdir prisma_quitckstart
cd prisma_quitckstart

## 初期化
npm init -y 
npm install typescript ts-node @types/node --save-dev

## TypeScriptの初期設定
npx tsc --init

## Prisma CLI のインストール
npm install prisma --save-dev

## prisma のセットアップ(sqliteで実行させる)
npx prisma init --datasource-provider sqlite



## Prisma スキーマでデータをモデル化する
prisma/schema.prisma を作成して記述


## risma Migrate でデータベース テーブルを作成
npx prisma migrate dev --name init


## Prisma Client を使用してデータベースにクエリを実行する
〇データの作成
$ npx ts-node script1.ts 
{ id: 1, email: 'alice@prisma.io', name: 'Alice' }

〇データの取得
$ npx ts-node script2.ts 
[{ id: 1, email: 'alice@prisma.io', name: 'Alice' }]

〇リレーションのデータ作成
$ npx ts-node script3.ts 
{ id: 2, email: 'bob@prisma.io', name: 'Bob' }


〇ネストしたデータの取得
$ npx ts-node script4.ts 
[
  { id: 1, email: 'alice@prisma.io', name: 'Alice', posts: [] },
  {
    id: 2,
    email: 'bob@prisma.io',
    name: 'Bob',
    posts: [
      {
        id: 1,
        title: 'Hello World',
        content: null,
        published: false,
        authorId: 2
      }
    ]
  }
]


## prisma studio を使う
WEB上でデータを見たり操作が出来る様になる
npx prisma studio
