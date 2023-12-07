```typescript
type CreateIcognito {
	typeID: 18
	groupSize: UnsignedInteger
	areaID: UnsignedInteger
	{
		userID: UnsignedInteger
		key: PublicKey
	}[]
}
```

Komenda grupy użytkowników

Aby komenda była poprawna każde z kont biorących udział w tworzeniu musi posiadać prawo do głosu w skazanym `areaID`

