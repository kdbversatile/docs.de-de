---
title: Onlinesicherung
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie das Feature für die Online Sicherung von SQLite verwenden.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901286"
---
# <a name="online-backup"></a>Onlinesicherung

SQLite kann Datenbankdateien sichern, während die app ausgeführt wird. Diese Funktion ist in Microsoft. Data. sqlite als <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> Methode auf `SqliteConnection`verfügbar.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Zurzeit werden `BackupDatabase` die Datenbank so schnell wie möglich sichern und andere Verbindungen daran hindert, in die Datenbank zu schreiben. Problem [#13834](https://github.com/dotnet/efcore/issues/13834) wäre eine Alternative API zum Sichern der Datenbank im Hintergrund und ermöglicht anderen Verbindungen das Unterbrechen der Sicherung und das Schreiben in die Datenbank. Wenn Sie interessiert sind, geben Sie uns Feedback zu diesem Problem.
