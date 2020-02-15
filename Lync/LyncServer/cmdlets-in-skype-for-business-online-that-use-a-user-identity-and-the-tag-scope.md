---
title: Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden
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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001440"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden

 


Die **Grant-CS-** Cmdlets (zum Zuweisen von Richtlinien zu Benutzern) erfordern zwei Bezeichner: eine Benutzeridentität (der Parameter Identity) und die Identität einer benutzerspezifischen Richtlinie (dem Parameter PolicyName). Um beispielsweise die VoIP-Richtlinie "redmondvoicepolicy" dem Benutzer Ken Myers zuzuweisen, verwenden Sie den folgenden Befehl:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Beim Zuweisen von Richtlinien zu Benutzern müssen zwei Punkte beachtet werden. Zunächst können nur benutzerspezifische Richtlinien zugewiesen werden. Sie können die globale Richtlinie keinem Benutzer zuweisen. Beispielsweise tritt bei diesem Befehl ein Fehler auf:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Dieser Befehl schlägt fehl, da es nicht erforderlich ist, die globale Richtlinie zuzuweisen. Wenn Sie einen Benutzer mithilfe der globalen Richtlinie verwalten möchten, achten Sie darauf, dass Sie diesem Benutzer keine Richtlinien auf Benutzerebene zuweisen. Wenn einem Benutzer keine benutzerspezifische Richtlinie zugewiesen wurde, wird der Benutzer automatisch mithilfe der globalen Richtlinie verwaltet.


> [!NOTE]  
> Was geschieht, wenn dem Benutzer zuvor eine benutzerspezifische Richtlinie zugewiesen wurde und Sie die Zuweisung dieser Richtlinie aufheben und stattdessen den Benutzer von der globalen Richtlinie verwalten lassen möchten? In diesem Fall verwenden Sie zunächst die folgende Syntax, die die Zuweisung einer benutzerbasierten Richtlinie aufheben, indem Sie dem Benutzer eine NULL-Richtlinie gewährt:<BR>Grant-CsVoicePolicy – Identity "Ken Myers" – Richtlinienname $NULL



Beachten Sie Zweitens, dass benutzerspezifische Richtlinien auf dem Tag-Bereich erstellt werden. Sie können **das Tagpräfix jedoch beim angeben** eines Richtlinien namens weglassen. Diese beiden Befehle sind identisch:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Wenn Sie die Identitäten für alle Richtlinien auf Benutzerebene (oder zumindest alle benutzerspezifischen Richtlinien des angegebenen Typs, beispielsweise VoIP-Richtlinien) zurückgeben möchten, verwenden Sie einen Befehl wie den folgenden:

    Get-CsVoicePolicy -Filter "tag:*"

Die folgenden Cmdlets verwenden sowohl eine Benutzeridentität als auch den Tag-Bereich:

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

