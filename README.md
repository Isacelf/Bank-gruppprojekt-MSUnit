## Affärskritiska delar och möjliga fel

### Deposit
- **Affärskritisk del:** Insättning av pengar på ett konto.
- **Möjliga fel:** 
  - Felaktigt konto valdes (index utanför gränserna).
  - Ogiltigt belopp inskrivet (icke-numeriskt värde).
  - Insättning till ett icke-existerande konto.

### Withdraw
- **Affärskritisk del:** Uttag av pengar från ett konto.
- **Möjliga fel:** 
  - Felaktigt konto valdes (index utanför gränserna).
  - Ogiltigt belopp inskrivet (icke-numeriskt värde).
  - Uttag av mer pengar än vad som finns på kontot (otillräckliga medel).
  - Uttag från ett icke-existerande konto.

### CreateUser
- **Affärskritisk del:** Skapande av en ny användare.
- **Möjliga fel:** 
  - Ogiltigt användarnamn (mindre än två bokstäver).
  - Ogiltig PIN-kod (inte exakt fyra siffror).
  - Användarnamn redan taget.

## Tester

För att säkerställa att dessa affärskritiska delar fungerar korrekt har vi implementerat enhetstester med MSTest. Dessa tester kontrollerar att fel hanteras korrekt och att korrekta operationer utförs på rätt sätt.

- Tester för `Deposit`-metoden kontrollerar att insättning till rätt konto ökar saldot, samt att felaktiga konton eller belopp inte påverkar saldot.
- Tester för `Withdraw`-metoden kontrollerar att uttag från rätt konto minskar saldot, samt att otillräckliga medel eller felaktiga konton inte påverkar saldot.
- Tester för `CreateUser`-metoden kontrollerar att användare med giltiga uppgifter skapas korrekt, samt att ogiltiga uppgifter eller redan använda användarnamn inte tillåts.
