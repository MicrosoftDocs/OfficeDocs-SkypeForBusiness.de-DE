---
title: Verwenden von PowerShell für Aufgaben im Menü "Überwachung und Archivierung"
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
description: 'Zusammenfassung: Skype for Business Server Systemsteuerung zur Cmdlet-Zuordnung für das Menü "Überwachung und Archivierung".'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626233"
---
# <a name="monitoring-and-archiving"></a>Überwachen und Archivieren

In diesem Artikel wird beschrieben, wie ähnliche Ergebnisse wie die des Menüelements **"Überwachung und Archivierung"** in der älteren Systemsteuerung mithilfe von Cmdlets erzielt werden können.

In diesem Artikel werden die folgenden Untermenüs beschrieben:

- [Überwachung und Archivierung](#monitoring-and-archiving)
  - [Aufzeichnung von Kommunikationsdatensätzen](#call-detail-recording)
  - [Quality of Experience-Daten](#quality-of-experience-data)
  - [Archivierungsrichtlinie](#archiving-policy)
  - [Archivierungskonfiguration](#archiving-configuration)

## <a name="call-detail-recording"></a>Aufzeichnung von Kommunikationsdatensätzen

Mit dem Untermenü **"AUFZEICHNUNG** VON KOMMUNIKATIONSDATENSÄTZEN" können Administratoren Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen (KDS) verwalten. Mit KDS können Sie die Verwendung von Peer-to-Peer-Chatsitzungen, VoIP-Telefonanrufen (Voice over Internet Protocol) und Konferenzanrufen nachverfolgen.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer bei der AUFZEICHNUNG von **KOMMUNIKATIONSDATENSÄTZEN** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller KDS-Konfigurationen

   ![Konfiguration von KDs auflisten](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Beispiel***

```powershell
 Get-CsCdrConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen KDS-Konfiguration

   ![Erstellen der KDS-Konfiguration](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Beispiel***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten KDS-Konfiguration

   ![Abrufen der KDS-Konfiguration](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Beispiel***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Ausgewählte KDS-Konfigurationen löschen

   ![Löschen der KDS-Konfiguration](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Beispiel***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer KDS-Konfiguration

   ![Aktualisieren der KDS-Konfiguration](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Beispiel***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Quality of Experience-Daten

Mit dem Untermenü **"QUALITY OF EXPERIENCE DATA"** können Administratoren QoE-Einstellungen (Quality of Experience) verwalten. in der gesamten Organisation; Dazu gehören die Verwaltung der Gruppenerweiterung, Zertifikateinstellungen und zulässigen Authentifizierungsmethoden. Da Administratoren unterschiedliche Einstellungen auf globaler, Standort- und Dienstebene konfigurieren können (allerdings nur für den Webdienstdienst), können Webdienstfunktionen für unterschiedliche Benutzer und unterschiedliche Speicherorte angepasst werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer in **WEB SERVICE** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---
> **Szenario 1:** Auflisten aller QoE-Konfigurationen

   ![QoE-Konfiguration auflisten](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Beispiel***

```powershell
 Get-CsQoEConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen QoE-Konfiguration

   ![Neue QoE-Konfiguration](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Beispiel***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten QoE-Konfiguration

   ![QoE-Konfiguration abrufen](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Beispiel***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Ausgewählte QoE-Konfigurationen löschen

   ![Löschen der QoE-Konfiguration](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Beispiel***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer QoE-Konfiguration

   ![QoE-Konfiguration aktualisieren](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Beispiel***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Archivierungsrichtlinie

Administratoren können **ARCHIVIERUNGSRICHTLINIEN** verwenden, um Archivierungsrichtlinien für Chatsitzungen zu verwalten. Mit Archivierungsrichtlinien können Sie alle Chat- und Webkonferenzsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer für **ARCHIVIERUNGSRICHTLINIEN** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Archivierungsrichtlinien

   ![Archivierungsrichtlinie auflisten](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Beispiel***

```powershell
 Get-CsArchivingPolicy
```

---

> **Szenario 2:** Erstellen einer neuen Archivierungsrichtlinie

   ![Erstellen einer Archivierungsrichtlinie](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Beispiel***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Archivierungsrichtlinie

   ![Archivierungsrichtlinie abrufen](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Beispiel***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter Archivierungsrichtlinien

   ![Archivierungsrichtlinie löschen](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Beispiel***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Archivierungsrichtlinie

   ![Aktualisieren der Archivierungsrichtlinie](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Beispiel***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Archivierungskonfiguration

Administratoren können **die ARCHIVIERUNGSKONFIGURATION** verwenden, um zu konfigurieren, wie (oder ob) Chatsitzungen in der Organisation archiviert werden.

Betrachten wir die verschiedenen Aufgaben, die ein Benutzer bei der **ARCHIVIERUNGsKONFIGURATION** ausführen kann, und die Skype for Business Cmdlets, denen diese Aufgaben zugeordnet sind.

---

> **Szenario 1:** Auflisten aller Archivierungskonfigurationen

   ![Archivierungskonfiguration auflisten](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Beispiel***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Szenario 2:** Erstellen einer neuen Archivierungskonfiguration

   ![Erstellen der Archivierungskonfiguration](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Beispiel***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Szenario 3:** Abrufen von Details zu einer ausgewählten Archivierungskonfiguration

   ![Archivierungskonfiguration abrufen](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Beispiel***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Szenario 4:** Löschen ausgewählter Archivierungskonfigurationen

   ![Archivierungskonfiguration löschen](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Beispiel***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Szenario 5:** Aktualisieren einer Archivierungskonfiguration

   ![Aktualisieren der Archivierungskonfiguration](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Beispiel***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
