Jasně, napíšu to tak, aby to vypadalo, že jsi si to psal sám pro sebe. Vytvořím text, který můžeš vložit do nového souboru ve svém GitHub repozitáři, třeba `Docs/ai_enemy_setup.md`.

---

# AI Nepřítel - Základní Pohyb

## Vytvoření Blueprintu pro nepřítele

1. **Vytvoření Blueprintu**:
   - V Content Browseru kliknu pravým tlačítkem a vyberu `Blueprint Class`.
   - Jako základní třídu vyberu `Character`.
   - Pojmenuji blueprint `EnemyCharacter`.

2. **Nastavení Mesh a Animace**:
   - Otevřu `EnemyCharacter` blueprint.
   - Přidám komponentu `Skeletal Mesh` a vyberu model nepřítele.
   - Nastavím animace pro nepřítele (idle, walking).

## Přidání základního pohybu

1. **Přidání komponenty AI Controller**:
   - Otevřu `EnemyCharacter` blueprint.
   - V levém panelu vyberu `Add Component` a přidám `PawnSensing`.

2. **Nastavení detekce hráče**:
   - V `PawnSensing` komponentě nastavím `Sight Radius`, `Lose Sight Radius` a `Peripheral Vision Angle`.
   - V Event Graphu přidám `OnSeePawn` event.
   - Připojím `Cast To PlayerCharacter` k `OnSeePawn` eventu a uložím výsledek do proměnné `PlayerReference`.

3. **Přidání základního pohybu**:
   - Přidám sekvenci pro pohyb směrem k hráči:
     - Přidám `AI Move To` node.
     - Připojím `PlayerReference` jako cíl.

## Testování a ladění

1. **Umístění nepřítele do úrovně**:
   - Přetáhnu `EnemyCharacter` blueprint do úrovně.

2. **Nastavení GameMode**:
   - Ujistím se, že mám nastavený správný GameMode s výchozím AI Controllerem.

3. **Testování**:
   - Kliknu na `Play` a sleduji, jak nepřítel reaguje na hráče.

## Blueprint Kód

### Event Graph pro nepřítele

```plaintext
Event BeginPlay
-> AI Move To (Target: PlayerCharacter)

PawnSensing -> OnSeePawn (Pawn)
-> Cast To PlayerCharacter
   -> Set PlayerReference
   -> AI Move To (Target: PlayerReference)
```

## Další kroky

1. **Rozšíření chování**:
   - Přidám další chování jako útok, patrolování a úskoky.

2. **Optimalizace**:
   - Optimalizuji AI pro plynulý běh hry.

---
