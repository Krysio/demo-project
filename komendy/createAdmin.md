```typescript
type CreateAdmin {
	typeID: 16
	userID: UnsignedInteger
	level: UnsignedInteger
	key: PublicKey
	timeStart: UnsignedInteger
	timePeriod: UnsignedInteger
	meta: String
}
```

Komenda administratora

pula `userID` jest współdzielona między administratorami a użytkownikami
`level` posiada zawsze niższą wartość niż konto tworzące
przy użyciu `timeStart` oraz `timePeriod` definiowany jest czas życia konta, może być nie ustalony dla wyższych kont
`meta` Zawiera dane wskazujące na właściciela konta