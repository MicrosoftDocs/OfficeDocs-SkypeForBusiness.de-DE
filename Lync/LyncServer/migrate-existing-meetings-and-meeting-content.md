---
title: Migrieren von vorhandenen Besprechungen und Besprechungsinhalten
TOCTitle: Migrieren von vorhandenen Besprechungen und Besprechungsinhalten
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49890686
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von vorhandenen Besprechungen und Besprechungsinhalten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Wenn ein Benutzerkonto von Lync Server 2010 auf einen Lync Server 2013-Server verschoben wird, werden die folgenden Informationen zusammen mit dem Benutzerkonto verschoben:

  - **Vom Benutzer bereits geplante Besprechungen :** Dies beinhaltet das Verschieben von Konferenzverzeichnissen und Konferenzdaten.

  - **Die persönliche Identifikationsnummer (PIN) des Benutzers :** Die aktuelle PIN des Benutzers ist weiterhin solange gültig, bis sie abläuft oder der Benutzer eine neue PIN anfordert.

Die folgenden Benutzerkontoinformationen werden nicht auf den neuen Server verschoben:

  - **Besprechungsinhalte :** Um den während einer Besprechung freigegebenen Inhalt zu verschieben, z. B. PowerPoint- oder Whiteboard-Inhalt, Anlagen oder Umfragedaten, verwenden Sie den **-MoveConferenceData**-Parameter als Teil des **Move-CsUser**-Cmdlets.

