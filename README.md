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

### InitializeUsers
- **Affärskritisk del:** Initialisering av användare i systemet.
- **Möjliga fel:** 
  - Felaktigt antal användare initialiseras.
  - Felaktiga användarnamn eller pinkoder tilldelas användarna.

## Tester

För att säkerställa att dessa affärskritiska delar fungerar korrekt har vi implementerat enhetstester med MSTest. Dessa tester kontrollerar att fel hanteras korrekt och att korrekta operationer utförs på rätt sätt.

- Tester för `Deposit`-metoden kontrollerar att insättning till rätt konto ökar saldot, samt att felaktiga konton eller belopp inte påverkar saldot.
- Tester för `Withdraw`-metoden kontrollerar att uttag från rätt konto minskar saldot, samt att otillräckliga medel eller felaktiga konton inte påverkar saldot.
- Tester för `InitializeUsers`-metoden säkerställer att rätt antal användare initialiseras och att korrekta användarnamn och pinkoder tilldelas dem.

