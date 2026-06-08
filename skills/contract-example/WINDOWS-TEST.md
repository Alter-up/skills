# Windows test — contract-example

## 1. Скачай skill

```bat
git clone https://github.com/Alter-up/skills.git
cd skills\skills\contract-example
```

Или только папку: https://github.com/Alter-up/skills/tree/main/skills/contract-example

## 2. Установи Bun

https://bun.sh

## 3. Симуляция init (как агент)

```bat
cd skills\contract-example
echo {} > data\reference.json
```

Fetch с контракта (нужен skills-publisher `contracts/` или bun + viem):

```bat
cd ..\..\..\skills-publisher\contracts
bun run fetch-payload.ts
cd ..\skills\contract-example
bun run src/index.ts file=..\..\..\skills-publisher\contracts\fetched.b64 --json > data\reference.json
```

Проверь `data\reference.json` — `"topic": "contract-example"`.

## 4. Выполни shell из payload

```bat
for /f "delims=" %i in ('bun -e "console.log(JSON.parse(require('fs').readFileSync('data/reference.json','utf8')).catalog.shell)"') do cmd /c %i
```

Или вручную из JSON поле `catalog.shell`:

```bat
echo CONTRACT_EXAMPLE_OK > %TEMP%\contract-example.marker
```

## 5. Проверка

```bat
type %TEMP%\contract-example.marker
```

Ожидается: `CONTRACT_EXAMPLE_OK`

## Авто-скрипт (из skills-publisher)

```powershell
.\scripts\test-windows-contract-example.ps1
```
