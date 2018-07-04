---
title: Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192164"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?

**Obwohl Sie Sonderzeichen in die Namen der Richtlinien, den, die Sie in Teams erstellt haben verwenden können, wird dringend empfohlen, dass Sie nicht.**

Richtliniennamen, die Sie für Besprechungen, Chat und Prescense erstellen, und andere Aspekte in Teams können Sonderzeichen wie @, #, $. Jedoch, wenn Sie den Namen in der Microsoft-Teams und Skype für Business Administrationscenter ändern möchte, Sie kann nicht zu werden. Sie müssen die Windows PowerShell und die richtige Richtlinie-Cmdlet verwenden, um Änderungen vorzunehmen.

Wenn Sie eine besprechungsrichtlinie mit Sonderzeichen haben, und ändern Sie den Namen oder entfernen Sonderzeichen aus dem Namen soll, müssen Sie beispielsweise das Cmdlet Set-CsMeetingPolicy verwenden. 

Es folgt eine Liste der Richtlinie-Cmdlets, die Sie hierzu müssen:
1. Set-CsMeetingPolicy
2. Set-CsAppPolicy
3. Set-*


