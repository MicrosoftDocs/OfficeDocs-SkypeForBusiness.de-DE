---
title: Erstellen von Konferenzverzeichnissen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Zusammenfassung: Erfahren Sie, wie konferenzverzeichnisse in Skype für Business Server 2015 zu erstellen.'
ms.openlocfilehash: 861172a76da68d39fd9f8213de6e45a892aa1780
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568745"
---
# <a name="create-conference-directories-in-skype-for-business-server-2015"></a><span data-ttu-id="db425-103">Erstellen von Konferenzverzeichnissen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="db425-103">Create conference directories in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="db425-104">**Zusammenfassung:** Erfahren Sie, wie konferenzverzeichnisse in Skype für Business Server 2015 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db425-104">**Summary:** Learn how to create conference directories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="db425-105">Konferenzverzeichnisse verwalten eine Zuordnung zwischen alphanumerische besprechungs-ID, die ein Teilnehmer an einer Konferenz teilnehmen, bei Verwendung von Skype für Unternehmen verwendet und die numerische Konferenz-ID, einwahlkonferenzen Teilnehmer an der Konferenz teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="db425-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="db425-106">Ein Konferenzverzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="db425-106">Create a conference directory</span></span>

<span data-ttu-id="db425-107">Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db425-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="db425-p101">In einer Organisation mit einer typischen Konferenzanzahl pro Nutzer wird empfohlen, pro 999 Nutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="db425-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="db425-111">Das Format einer Konferenz-ID lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="db425-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="db425-p102">Verwenden Sie das Cmdlet **New-CsConferenceDirectory**, um ein Konferenzverzeichnis zu erstellen. So wird zum Beispiel über den folgenden Befehl ein neues Konferenzverzeichnis mit dem Identitätswert 42 erstellt, das im Pool „atl-cs-001.litwareinc.com“ gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="db425-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="db425-114">Weitere Informationen finden Sie unter [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="db425-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

