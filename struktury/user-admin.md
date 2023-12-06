Struktura bazy danych

```typescript
type UserAdmin {
	type: 1
	userID: UnsignedInteger
	level: UnsignedInteger
	key: PublicKey
	timeStart: UnsignedInteger
	timeEnd: UnsignedInteger
	parent: UnsignedInteger
	meta: String
}
```

Konto administratora służy do wprowadzania zwykłych użytkowników do systemu.
Może posiadać wyznaczony czas życia konta.

Właściwość `level` oznacza poziom hierarchii danego konta.
`parent` oznacza ID konta, które to konto wykreowało.
`meta` Dane personalne danego konta.

Pula `userID` jest współdzielona między administratorami a użytkownikami.

