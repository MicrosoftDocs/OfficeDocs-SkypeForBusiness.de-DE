---
title: Erstellen von Konferenzverzeichnissen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Zusammenfassung: Erfahren Sie, wie Sie Konferenzverzeichnisse in Skype for Business Server erstellen.'
ms.openlocfilehash: b1b1a09b00a7b0c87caff474d52e000db1e95a4a79ba8e54cb4a15a3f4ca32de
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319108"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Erstellen von Konferenzverzeichnissen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Konferenzverzeichnisse in Skype for Business Server erstellen.
  
Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz verwendet, wenn er Skype for Business verwendet, und der rein numerischen Konferenz-ID, die ein Einwahlkonferenzteilnehmer für die Teilnahme an der Konferenz verwendet. 
  
## <a name="create-a-conference-directory"></a>Erstellen eines Konferenzverzeichnisses

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. 
  
Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Mit dieser Richtlinie können die Konferenz-IDs in der Regel klein gehalten werden. Sobald die Anzahl der Konferenzverzeichnisse (in allen Pools) jedoch 9 überschreitet, wird die Konferenz-ID größer, um zusätzliche Konferenzen zu unterstützen.
  
Das Format einer Konferenz-ID lautet wie folgt: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Verwenden Sie zum Erstellen eines Konferenzverzeichnisses das Cmdlet **"New-CsConferenceDirectory".** Mit dem folgenden Befehl wird beispielsweise ein Konferenzverzeichnis mit der Identität 42 erstellt, das im Pool atl-cs-001.litwareinc.com gehostet wird:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Weitere Informationen finden Sie unter [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
