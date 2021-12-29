---
title: Verwenden von PowerShell für Aufgaben im Topologiemenü
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für das Topologiemenü.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626226"
---
# <a name="topology"></a>Topologie

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie mit dem Menüelement **"Topologie"** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Topologie](#topology)
  - [Status](#status)
  - [Serveranwendung](#server-application)
  - [Einfache URL](#simple-url)
  - [Vertrauenswürdige Anwendung](#trusted-application)

## <a name="status"></a>Status

**Mit** dem Status-Untermenü können Administratoren die Computer in der Topologie verwalten.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **STATUS** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Computer und deren Status

   ![Computer und Status auflisten](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Beispiel***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Beispiel***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Beispiel***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Serveranwendung

Serveranwendungen beziehen sich auf die einzelnen Programme, die unter Skype for Business Server ausgeführt werden. Das Untermenü **"SERVERANWENDUNG"** bietet Administratoren die Möglichkeit, Informationen zu allen anwendungen zurückzugeben, die als Teil Skype for Business Server ausgeführt werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer auf **SERVER APPLICATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Serveranwendungen

   ![List Server-Anwendung](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Beispiel***

```powershell
 Get-CsServerApplication
```

---

> **Szenario 2:** Aktivieren/Deaktivieren oder Auswählen von kritisch/Aufheben der Auswahl einer kritischen Serveranwendung

   ![Bearbeiten der Serveranwendung](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Beispiel***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>Einfache URL

Einfache URLs erleichtern Benutzern die Teilnahme an Besprechungen und Konferenzen und erleichtern Administratoren die Anmeldung bei der Skype for Business Server Systemsteuerung.Das Untermenü **"EINFACHE URL"** hilft Administratoren, diese anzuzeigen.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **einfacher URL** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller Konfigurationen für einfache URLs

   ![Einfache URL auflisten](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Beispiel***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Vertrauenswürdige Anwendung

Bei einer vertrauenswürdigen Anwendung handelt es sich um eine von einem Drittanbieter entwickelte Anwendung, deren vertrauenswürdiger Status als Teil der Skype for Business Server ausgeführt werden kann, die jedoch kein integrierter Bestandteil des Produkts ist. Das Untermenü **"VERTRAUENSWÜRDIGE ANWENDUNG"** hilft Administratoren, sie anzuzeigen.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer mit **TRUSTED APPLICATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller vertrauenswürdigen Anwendungen

   ![Vertrauenswürdige Anwendung auflisten](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Beispiel***

```powershell
 Get-CsTrustedApplication
```

---
