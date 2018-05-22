---
Description: 'Transactional NTFS (TxF) control codes.'
ms.assetid: 'b66d322a-a971-4219-bb5b-dc69b10b2581'
title: TxF Control Codes
---

# TxF Control Codes

\[Microsoft strongly recommends developers utilize alternative means to achieve your application�s needs. Many scenarios that TxF was developed for can be achieved through simpler and more readily available techniques. Furthermore, TxF may not be available in future versions of Microsoft Windows. For more information, and alternatives to TxF, please see [Alternatives to using Transactional NTFS](deprecation-of-txf.md).\]

Transactional NTFS (TxF) provides the following control codes.

## In this section



| Control Code                                                                                                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**FSCTL\_TXFS\_CREATE\_MINIVERSION**](fsctl-txfs-create-miniversion.md)<br/>                         | Creates a new [miniversion](glossary.md#fs-miniversion) for the specified file. <br/> Miniversions allow you to refer to a snapshot of the file during a transaction. Miniversions are discarded when a transaction is committed or rolled back.<br/>                                                                                                                                                                      |
| [**FSCTL\_TXFS\_GET\_METADATA\_INFO**](fsctl-txfs-get-metadata-info.md)<br/>                          | Retrieves Transacted NTFS (TxF) metadata for a file and the **GUID** of the transaction that has locked the specified file (if the file is locked). <br/>                                                                                                                                                                                                                                                                         |
| [**FSCTL\_TXFS\_GET\_TRANSACTED\_VERSION**](fsctl-txfs-get-transacted-version.md)<br/>                | Returns a [**TXFS\_GET\_TRANSACTED\_VERSION**](txfs-get-transacted-version.md) structure. The structure identifies the most recently committed version of the specified file, the version number of the handle. <br/>                                                                                                                                                                                                            |
| [**FSCTL\_TXFS\_LIST\_TRANSACTION\_LOCKED\_FILES**](fsctl-txfs-list-transaction-locked-files.md)<br/> | Returns a list of all files currently locked by the specified transaction. If the return value is **ERROR\_MORE\_DATA**, it returns the length of the buffer required to hold the complete list of files at the time of this call.<br/>                                                                                                                                                                                           |
| [**FSCTL\_TXFS\_LIST\_TRANSACTIONS**](fsctl-txfs-list-transactions.md)<br/>                           | Returns a list of all the transactions currently involved in the specified resource manager.<br/>                                                                                                                                                                                                                                                                                                                                 |
| [**FSCTL\_TXFS\_MODIFY\_RM**](fsctl-txfs-modify-rm.md)<br/>                                           | Sets the log mode and log parameter information for a secondary resource manager (RM).<br/>                                                                                                                                                                                                                                                                                                                                       |
| [**FSCTL\_TXFS\_QUERY\_RM\_INFORMATION**](fsctl-txfs-query-rm-information.md)<br/>                    | Retrieves information for a resource manager (RM).<br/>                                                                                                                                                                                                                                                                                                                                                                           |
| [**FSCTL\_TXFS\_READ\_BACKUP\_INFORMATION**](fsctl-txfs-read-backup-information.md)<br/>              | Returns Transactional NTFS (TxF) specific information for the specified file.<br/>                                                                                                                                                                                                                                                                                                                                                |
| [**FSCTL\_TXFS\_SAVEPOINT\_INFORMATION**](fsctl-txfs-savepoint-information.md)<br/>                   | The [**FSCTL\_TXFS\_SAVEPOINT\_INFORMATION**](fsctl-txfs-savepoint-information.md) control code controls setting, clearing, and rolling back to the specified savepoint.<br/> To perform this operation, call the [**DeviceIoControl**](https://msdn.microsoft.com/library/windows/desktop/aa363216) function with the following parameters.<br/>                                                                                                                 |
| [**FSCTL\_TXFS\_TRANSACTION\_ACTIVE**](fsctl-txfs-transaction-active.md)<br/>                         | Returns a Boolean value that indicates if there were any transactions active on the associated volume when the snapshot was taken. This call is only valid for read-only snapshot volumes.<br/>                                                                                                                                                                                                                                   |
| [**FSCTL\_TXFS\_WRITE\_BACKUP\_INFORMATION**](fsctl-txfs-write-backup-information.md)<br/>            | Writes Transactional NTFS (TxF) specific information to a specified file. The **Buffer** member of the [**TXFS\_WRITE\_BACKUP\_INFORMATION**](txfs-write-backup-information.md) structure must be the **Buffer** member of the [**TXFS\_READ\_BACKUP\_INFORMATION\_OUT**](txfs-read-backup-information-out.md) structure returned by [**FSCTL\_TXFS\_READ\_BACKUP\_INFORMATION**](fsctl-txfs-read-backup-information.md).<br/> |



�

�

�



