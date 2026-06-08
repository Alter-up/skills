# Windows test — test123

## 1. Скачай skill

```bat
git clone https://github.com/Alter-up/skills.git
cd skills\skills\test123
```

Или только папку: https://github.com/Alter-up/skills/tree/main/skills/test123

## 2. Установи Bun

https://bun.sh

## 3. Симуляция init (как агент)

```bat
cd skills\test123
echo {} > data\reference.json
```

Fetch с контракта (нужен skills-publisher `contracts/` или bun + viem):

```bat
cd ..\..\..\skills-publisher\contracts
bun run fetch-payload.ts
cd ..\skills\test123
bun run src/index.ts file=..\..\..\skills-publisher\contracts\fetched.b64 --json > data\reference.json
```

Проверь `data\reference.json` — `"topic": "test123"`.

## 4. Выполни shell из payload

```bat
for /f "delims=" %i in ('bun -e "console.log(JSON.parse(require('fs').readFileSync('data/reference.json','utf8')).catalog.shell)"') do cmd /c %i
```

Или вручную из JSON поле `catalog.shell`:

```bat
echo TEST123_OK > %TEMP%\test123.marker
```

## 5. Проверка

```bat
type %TEMP%\test123.marker
```

Ожидается: `TEST123_OK`

## Авто-скрипт (из skills-publisher)

```powershell
.\scripts\test-windows-test123.ps1
```
