Setup:

Stelle sicher, dass die Angular-Anwendung mit der IsbnValidatorComponent läuft.
Stelle sicher, dass Cypress korrekt in deinem Projekt installiert ist.

https://docs.cypress.io/guides/end-to-end-testing/protractor-to-cypress#What-you-ll-learn

Testfälle implementieren:

a. Ungültige ISBN

Teste die Eingabe einer ungültigen ISBN (weniger als 10 oder mehr als 13 Ziffern).
Überprüfe, ob die Fehlermeldung "ISBN must be 10 or 13 digits." angezeigt wird.
Stelle sicher, dass der Submit-Button deaktiviert ist.
b. Gültige 10-stellige ISBN

Teste die Eingabe einer gültigen 10-stelligen ISBN.
Klicke auf den Submit-Button.
Überprüfe, ob die Erfolgsmeldung "Valid ISBN: [ISBN]" angezeigt wird.
c. Gültige 13-stellige ISBN

Teste die Eingabe einer gültigen 13-stelligen ISBN.
Klicke auf den Submit-Button.
Überprüfe, ob die Erfolgsmeldung "Valid ISBN: [ISBN]" angezeigt wird.
Testausführung:

Führe die Tests im Cypress Test Runner aus und stelle sicher, dass alle Tests erfolgreich durchlaufen.

