---
title: Erstellen von Konferenz Verzeichnissen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzverzeichnisse erstellen.'
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991850"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="da11d-103">Erstellen von Konferenz Verzeichnissen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="da11d-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="da11d-104">**Zusammenfassung:** Informationen zum Erstellen von Konferenz Verzeichnissen in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="da11d-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="da11d-105">Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz bei Verwendung von Skype for Business verwendet, und der numerischen Konferenz-ID, die ein Teilnehmer für Einwahlkonferenzen verwendet, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="da11d-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="da11d-106">Ein Konferenzverzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="da11d-106">Create a conference directory</span></span>

<span data-ttu-id="da11d-107">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="da11d-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="da11d-p101">In einer Organisation mit einer typischen Konferenzanzahl pro Nutzer wird empfohlen, pro 999 Nutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="da11d-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="da11d-111">Das Format einer Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="da11d-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="da11d-p102">Verwenden Sie das Cmdlet **New-CsConferenceDirectory**, um ein Konferenzverzeichnis zu erstellen. So wird zum Beispiel über den folgenden Befehl ein neues Konferenzverzeichnis mit dem Identitätswert 42 erstellt, das im Pool „atl-cs-001.litwareinc.com“ gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="da11d-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="da11d-114">Weitere Informationen finden Sie unter [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="da11d-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

