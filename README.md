## Student
- Name: Олексій Грицак Ростиславович
- Group: 232/2

## Практичне заняття №2 — NestJS + PostgreSQL + Redis

## Структура репозиторію
.
├── src/              	# NestJS source code
├── Dockerfile
├── docker-compose.yml
├── .env.example      	# шаблон змінних оточення
└── README.md

## Запуск проекту
[11:53:02 AM] Starting compilation in watch mode...
app-1  |
app-1  | [11:53:06 AM] Found 0 errors. Watching for file changes.
app-1  |
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [NestFactory] Starting Nest application...
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] TypeOrmModule dependencies initialized +108ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] ConfigHostModule dependencies initialized +1ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] AppModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] ConfigModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] CacheModule dependencies initialized +37ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] TypeOrmCoreModule dependencies initialized +92ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [RoutesResolver] AppController {/}: +10ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [RouterExplorer] Mapped {/, GET} route +7ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [NestApplication] Nest application successfully started +6ms                                                                                                                                                              
## Перевірка сервісів
NAME                        IMAGE                COMMAND                  SERVICE    CREATED          STATUS                    PORTS
hlpf-env-setup-app-1        hlpf-env-setup-app   "docker-entrypoint.s…"   app        2 minutes ago    Up 2 minutes              0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp
hlpf-env-setup-postgres-1   postgres:16-alpine   "docker-entrypoint.s…"   postgres   28 minutes ago   Up 28 minutes (healthy)   0.0.0.0:5432->5432/tcp, [::]:5432->5432/tcp
hlpf-env-setup-redis-1      redis:7-alpine       "docker-entrypoint.s…"   redis      28 minutes ago   Up 28 minutes (healthy)   0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp
## Перевірка PostgreSQL
 Name    |  Owner   | Encoding | Locale Provider |  Collate   |   Ctype    | ICU Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+------------+------------+------------+-----------+-----------------------
 nestdb    | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 postgres  | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 template0 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
 template1 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
(4 rows)
## Перевірка Redis
PS D:\hlpf-env-setup> docker compose exec redis redis-cli ping
PONG
## Перевірка застосунку
PS D:\hlpf-env-setup>  curl http://localhost:3000
Hello World!
## Логи NestJS (фрагмент)
[11:53:02 AM] Starting compilation in watch mode...
app-1  |
app-1  | [11:53:06 AM] Found 0 errors. Watching for file changes.
app-1  |
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [NestFactory] Starting Nest application...
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] TypeOrmModule dependencies initialized +108ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] ConfigHostModule dependencies initialized +1ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] AppModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] ConfigModule dependencies initialized +0ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] CacheModule dependencies initialized +37ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [InstanceLoader] TypeOrmCoreModule dependencies initialized +92ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [RoutesResolver] AppController {/}: +10ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [RouterExplorer] Mapped {/, GET} route +7ms
app-1  | [Nest] 29  - 03/31/2026, 11:53:08 AM     LOG [NestApplication] Nest application successfully started +6ms