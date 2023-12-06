Struktura bazy danych

```typescript
type User {
	type: 2
	userID: UnsignedInteger
	key: PublicKey
	areas: [sizeOfList: UnsignedInteger, UnsignedInteger[]]
	timeStart: UnsignedInteger
	timeEnd: UnsignedInteger
	parent: UnsignedInteger | null
	meta: String
}
```

Konto użytkownika systemu, mogą być one jawne lub anonimowe.

`areas` Lista obszarów, w których użytkownik posiada prawo głosu. Obszarem może być dziedzina lub mniejszy obszar administracyjny.

`parent` oznacza ID konta, które to konto wykreowało.
`meta` Dane personalne danego konta w przypadku konta jawnego.

Pula `userID` jest współdzielona między administratorami a użytkownikami.