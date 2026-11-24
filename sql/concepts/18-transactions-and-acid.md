# Transactions and ACID

A transaction groups database operations into one logical unit.

## ACID
- **Atomicity**: all operations succeed or none do.
- **Consistency**: constraints and rules remain satisfied.
- **Isolation**: concurrent transactions are controlled according to the isolation level.
- **Durability**: committed changes survive failures according to the database's durability guarantees.

## Example
```sql
BEGIN TRY
    BEGIN TRANSACTION;

    UPDATE dbo.Accounts
    SET Balance = Balance - 100
    WHERE AccountID = 1;

    UPDATE dbo.Accounts
    SET Balance = Balance + 100
    WHERE AccountID = 2;

    COMMIT TRANSACTION;
END TRY
BEGIN CATCH
    IF XACT_STATE() <> 0
        ROLLBACK TRANSACTION;

    THROW;
END CATCH;
```

## Isolation overview
SQL Server supports isolation levels including READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, SERIALIZABLE, and SNAPSHOT (when enabled). Higher isolation can reduce anomalies but may increase blocking or resource use.

## Practice
Simulate a transfer between two accounts and ensure a failure rolls back both updates.
