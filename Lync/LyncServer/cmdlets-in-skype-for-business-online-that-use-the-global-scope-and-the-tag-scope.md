---
title: Cmdlets, die den globalen Gültigkeitsbereich und den Tagbereich verwenden
TOCTitle: Cmdlets, die den globalen Gültigkeitsbereich und den Tagbereich verwenden
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56269254
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cmdlets, die den globalen Gültigkeitsbereich und den Tagbereich verwenden

 

_**Letztes Änderungsdatum des Themas:** 2015-06-22_

In Skype for Business Online können Richtlinien entweder im *globalen Gültigkeitsbereich* oder im *Tagbereich* (oder *benutzerbasierten Bereich*) konfiguriert werden. Bei Verwendung der **Get-Cs**-Cmdlets müssen Sie keinen Bereich und keine Identität angeben. Wenn Sie eines dieser Cmdlets ohne Parameter ausführen, werden alle relevanten Elemente zurückgegeben. So gibt dieser Befehl beispielsweise Informationen zu allen Ihren externen Zugriffsrichtlinien zurück:

    Get-CsExternalAccessPolicy

Sie müssen den Parameter **Identity** oder den Parameter **Filter** nur angeben, wenn Sie die zurückgegebenen Daten einschränken möchten. Wenn Sie beispielsweise nur die globale Richtlinie zurückgeben möchten, verwenden Sie den folgenden Befehl:

    Get-CsExternalAccessPolicy -Identity "global"

Wenn Sie eine benutzerbasierte Richtlinie mit der Identität **RedmondAccessPolicy** zurückgeben möchten, verwenden Sie diesen Befehl:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]
> Beim Verweis auf eine benutzerbasierte Richtlinie ist das Tag <STRONG>prefix</STRONG> optional. Die folgende Syntax, die das Präfix enthält, ist ebenfalls gültig:<BR>Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"



Wenn alle Richtlinien außer den globalen Richtlinien zurückgegeben werden sollen (d. h. alle benutzerbasierten Richtlinien), verwenden Sie den folgenden Befehl:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Die folgenden Cmdlets funktionieren sowohl im globalen, als auch im benutzerbasierten (Tag-) Bereich:

  - [Get-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientPolicy)

  - [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy)

  - [Get-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialPlan)

  - [Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

  - [Get-CsPresencePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPresencePolicy)

  - [Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)


> [!NOTE]
> Trotz des Namens sind Wählpläne, funktional gesehen, Richtlinien. Der Begriff <EM>Wählplan</EM> wird anstelle von Wählrichtlinie verwendet, um die Terminologie im Hinblick auf ältere Versionen von Lync Server konsistent zu halten.



## Siehe auch

#### Konzepte

[Identitäten, Bereiche und Mandanten](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Lync Online-Cmdlets](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

