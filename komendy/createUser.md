```typescript
type CreateUser {
	typeID: 17
	userID: UnsignedInteger
	key: PublicKey
	areas: [sizeOfList: UnsignedInteger, UnsignedInteger[]]
	meta: String
}
```

Komenda administratora

pula `userID` jest współdzielona między administratorami a użytkownikami
`areas` Lista obszarów gdzie mamy prawo głosu, dane województwo, powiat, gmina. Być może jakaś dziedzina jeśli dopuścimy elitaryzm w pewnych kwestiach
`meta` Zawiera dane wskazujące na właściciela konta