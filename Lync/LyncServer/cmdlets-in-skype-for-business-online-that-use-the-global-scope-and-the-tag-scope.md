---
title: Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001150"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden

 


In Skype for Business Online können Richtlinien entweder auf *globaler Ebene* oder auf dem *Tag-Bereich* (oder auf *Benutzerebene*) konfiguriert werden. Wenn Sie die Cmdlets " **Get-CS** " verwenden, müssen Sie keinen Bereich oder eine Identität angeben. Wenn Sie eines dieser Cmdlets ohne Parameter aufrufen, werden alle relevanten Elemente zurückgegeben. Mit diesem Befehl werden beispielsweise Informationen zu allen Richtlinien für den externen Zugriff zurückgegeben:

    Get-CsExternalAccessPolicy

Sie müssen nur den Parameter Identity oder den Parameter Filter einschließen, wenn Sie die zurückgegebenen Daten einschränken möchten. Um beispielsweise nur die globale Richtlinie zurückzugeben, verwenden Sie den folgenden Befehl:

    Get-CsExternalAccessPolicy -Identity "global"

Verwenden Sie den folgenden Befehl, um eine benutzerspezifische Richtlinie mit der Identität "RedmondAccessPolicy" zurückzugeben:

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Beim Verweisen auf eine benutzerspezifische Richt <STRONG>Linie ist das Tagpräfix optional</STRONG> . Diese Syntax, die das Präfix enthält, ist ebenfalls gültig:<BR>Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"



Verwenden Sie diesen Befehl, um alle Richtlinien mit Ausnahme der globalen Richtlinien (also aller benutzerspezifischen Richtlinien) zurückzugeben:

    Get-CsExternalAccessPolicy -Filter "tag:*"

Die folgenden Cmdlets funktionieren sowohl für den globalen Bereich als auch für den pro-Benutzer-(Tag-) Bereich:

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Trotz des Namens sind Wählpläne funktional gesehen Richtlinien. Der Begriff <EM>Wähl</EM> Einstellungen wird anstelle von, beispielsweise Wähl Richtlinie, verwendet, um die Terminologie beizubehalten, die in früheren Versionen von lync Server verwendet wurde.



## <a name="see-also"></a>Siehe auch


[Identitäten, Bereiche und Mandanten in Skype for Business Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Die Skype for Business Online-Cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

