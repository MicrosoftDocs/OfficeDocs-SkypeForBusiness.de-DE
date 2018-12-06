---
title: Cmdlets, die eine Benutzeridentität und den Tagbereich verwenden
TOCTitle: Cmdlets, die eine Benutzeridentität und den Tagbereich verwenden
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56269261
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, die eine Benutzeridentität und den Tagbereich verwenden

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

Die **Grant-Cs**-Cmdlets (mit denen Benutzern Richtlinien zugeordnet werden), setzen zwei Bezeichner voraus: eine Benutzeridentität (den Parameter **Identity**) und die Identität einer benutzerbasierten Richtlinie (der Parameter **PolicyName**). Um dem Benutzer Ken Myer beispielsweise die VoIP-Richtlinie **RedmondVoicePolicy** zuzuordnen, verwenden Sie den folgenden Befehl:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Bei der Zuordnung von Richtlinien zu Benutzern sind zwei Aspekte zu beachten. Zunächst einmal können nur benutzerbasierte Richtlinien zugeordnet werden. Sie können einem Benutzer keine globale Richtlinie zuordnen. So schlägt dieser Befehl beispielsweise fehl:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Dieser Befehl schlägt fehl, weil es keine Notwendigkeit gibt, eine globale Richtlinie zuzuordnen. Wenn Sie einen Benutzer mithilfe einer globalen Richtlinie verwalten möchten, stellen Sie einfach sicher, dass Sie diesem Benutzer keine benutzerbasierte Richtlinie zuordnen. Wenn dem Benutzer keine benutzerbasierte Richtlinie zugeordnet wurde, wird der Benutzer automatisch mit der globalen Richtlinie verwaltet.


> [!NOTE]
> Wie müssen Sie jedoch vorgehen, wenn dem Benutzer früher eine benutzerbasierte Richtlinie zugeordnet wurde und Sie die Zuordnung der Richtlinie nun aufheben möchten, damit der Benutzer nun mit der globalen Richtlinie verwaltet wird? In dem Fall verwenden Sie zuerst die folgende Syntax, mit der die Zuordnung der benutzerbasierten Richtlinie aufgehoben wird, indem dem Benutzer eine Null-Richtlinie zugeordnet wird:<BR>Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null



Denken Sie zum Zweiten daran, dass benutzerbasierte Richtlinien im Tagbereich erstellt werden. Sie können das Tag **prefix** jedoch auslassen, wenn Sie einen Richtliniennamen angeben. Diese beiden Befehle sind identisch:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Wenn Sie die Identitäten für alle benutzerbasierten Richtlinien zurückgeben möchten (oder zumindest für alle benutzerbasierten Richtlinien eines bestimmten Typs, wie VoIP-Richtlinien), verwenden Sie einen Befehl wie den folgenden:

    Get-CsVoicePolicy -Filter "tag:*"

Die folgenden Cmdlets verwenden sowohl eine Benutzeridentität als auch den Tagbereich:

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

