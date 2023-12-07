Administratora
```typescript
type AdminCommand {
	version: UnsignedInteger
	commandData: Buffer<auto>
	indexOfPrevBlock: UnsignedInteger
	userID: UnsignedInteger | UnsignedInteger[]
	signature: Buffer<auto> | Buffer<auto>[]
}
```

Użytkownika
```typescript
type AdminCommand {
	version: UnsignedInteger
	commandData: Buffer<auto>
	hashOfPrevBlock: Buffer<32>
	userID: UnsignedInteger | UnsignedInteger[]
	signature: Buffer<auto> | Buffer<auto>[]
}
```

Administrator nie powinien móc decydować, do którego bloku wprowadzi komendy, dlatego podpisuje on index ( heightID ) bloku.

Zależnie od typu komendy, autor może być jeden lub więcej razem z sygnaturami. Ilość autorów oraz sygnatur jest zawarta w `commandData` bezpośrednio po typie komendy

```typescript
interface UnsignedInteger; // kodowanie uleb128
interface Buffer<32>; // buffer o razmiarze 32 bajtów
interface Buffer<auto>; // zakodowanie rozmiaru buffer'a przy pomocy `uleb128` oraz ciągu bajtów w tej ilości.
```