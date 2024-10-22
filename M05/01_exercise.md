1. Formatierungsfunktion: Füge eine Funktion hinzu, die die ISBN formatiert, indem sie Bindestriche hinzufügt (z.B. 1234567890 zu 123-4567890123). Aktualisiere die submit()-Methode, um die formatierte ISBN anzuzeigen.

2. ISBN-Checker: Implementiere eine Funktion zur Validierung der ISBN-10 und ISBN-13-Nummern, die den Prüfwert überprüft.

3. Reset-Funktion: Implementiere eine reset()-Methode, die das Formular zurücksetzt (d.h. ISBN, Nachrichten und Status).

4. (Bonus) Visualisierung: Füge eine visuelle Rückmeldung hinzu, die das Eingabefeld rot einfärbt, wenn die ISBN ungültig ist.


```typescript
import { Component } from '@angular/core';
import {FormsModule} from "@angular/forms";
import {NgIf} from "@angular/common";

@Component({
  selector: 'app-isbn-validator',
  standalone: true,
  imports: [
    FormsModule,
    NgIf
  ],
  template: `
    <input [(ngModel)]="isbn" (ngModelChange)="checkIsbn()" placeholder="Enter ISBN"/>
    <div *ngIf="isInvalid && isbnTouched" style="color: red;">ISBN must be 10 or 13 digits.</div>
    <button (click)="submit()" [disabled]="isInvalid">Submit</button>
    <div *ngIf="message">{{ message }}</div>
  `
})
export class IsbnValidatorComponent {
  isbn: string = '';
  isInvalid: boolean = true;
  isbnTouched: boolean = false;
  message: string | null = null;

  checkIsbn() {
    this.isbnTouched = true;
    const digitsOnly = this.isbn.replace(/[^0-9]/g, ''); // Remove non-numeric characters
    this.isInvalid = digitsOnly.length !== 10 && digitsOnly.length !== 13; // Check for 10 or 13 digits
  }

  submit() {
    if (!this.isInvalid) {
      this.message = `Valid ISBN: ${this.isbn}`;
    }
  }
}
```