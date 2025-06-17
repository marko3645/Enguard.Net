# Enguard.Net

**A lightweight pattern for secure access to domain entities in .NET apps**

---

Enguard.Net helps you enforce access control for entities like `Person`, or `Template` directly in your business logic layer.

It’s a simple abstraction that:

* Lets you fetch an entity only if the current user has access
* Separates authorization from controllers and persistence
* Works great with Mediator and CQRS but is flexible enough to applied in any architecture

---

## Example

```csharp
var result = await this._provider
    .GetByIdAsync(entityId, currentUser)
    .ThrowIfNotFoundOrForbiddenAsync();

// use result
```

You write an implementation `ISecureEntityProvider<T>` per entity type, implementing logic to check access per user.

---

## Status

This project is a work in progress.

If it’s useful to you, feel free to watch or contribute. Feedback is welcome.

---

## License

MIT
