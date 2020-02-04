---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727565"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Transponder Bereich verwenden

 


Für die **Grant-CS-** Cmdlets (für die Zuweisung von Richtlinien für Benutzer) sind zwei Bezeichner erforderlich: eine Benutzeridentität (der Parameter Identity) und die Identität einer Richtlinie pro Benutzer (dem Parameter PolicyName). Um beispielsweise die VoIP-Richtlinie RedmondVoicePolicy dem Benutzer Ken Myers zuzuweisen, verwenden Sie den folgenden Befehl:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Beim Zuweisen von Richtlinien zu Benutzern müssen zwei Punkte beachtet werden. Zunächst können nur Richtlinien für einzelne Benutzer zugewiesen werden. Sie können die globale Richtlinie nicht einem Benutzer zuweisen. Dieser Befehl schlägt beispielsweise fehl:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Dieser Befehl schlägt fehl, da die globale Richtlinie nicht zugewiesen werden muss. Wenn Sie einen Benutzer mithilfe der globalen Richtlinie verwalten möchten, stellen Sie sicher, dass Sie diesem Benutzer keine Richtlinie pro Benutzer zuweisen. Wenn einem Benutzer keine benutzerspezifische Richtlinie zugewiesen wurde, wird der Benutzer automatisch mithilfe der globalen Richtlinie verwaltet.


> [!NOTE]  
> Was ist, wenn dem Benutzer zuvor eine Richtlinie pro Benutzer zugewiesen wurde und Sie die Zuweisung dieser Richtlinie aufheben und stattdessen den Benutzer von der globalen Richtlinie verwalten lassen möchten? In diesem Fall verwenden Sie zunächst die folgende Syntax, die die Zuweisung einer Richtlinie für einzelne Benutzer aufheben, indem Sie diesem Benutzer eine NULL-Richtlinie gewährt:<BR>Grant-CsVoicePolicy – Identity "Ken Myers" – Richtliniennamen $NULL



Beachten Sie Zweitens, dass Richtlinien für einzelne Benutzer im Bereich "Tag" erstellt werden. Sie können **das Tagpräfix jedoch bei der** Angabe eines Richtlinien namens weglassen. Diese beiden Befehle sind identisch:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Wenn Sie die Identitäten für alle Richtlinien für einzelne Benutzer zurückgeben möchten (oder zumindest alle Richtlinien für einzelne Benutzer, beispielsweise VoIP-Richtlinien), verwenden Sie einen Befehl, der wie folgt aussieht:

    Get-CsVoicePolicy -Filter "tag:*"

Die folgenden Cmdlets verwenden eine Benutzeridentität und den Tag-Bereich:

  - [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

