---
title: Die Cmdlets für die Skype for Business Online Berichterstellung und Rest-Webdienst
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbce4dda006bb45606a09eef29d8c47946ad2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Die Cmdlets für die Skype for Business Online Berichterstellung und Rest-Webdienst

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-09-05_

In Verbindung mit den Berichtsfeatures bietet Skype for Business Online Zugriff auf fünf Windows PowerShell-Cmdlets, mit denen diese Berichte generiert werden können und von Administratoren auch zum Zurückgeben benutzerdefinierter Berichtsdaten verwendet werden können. Skype for Business Online enthält auch den Rest (Representational State Transfer), der von Entwicklern zum Abrufen benutzerdefinierter Berichtsinformationen verwendet werden kann.

Die für Administratoren verfügbaren Berichts-Cmdlets umfassen Folgendes:

  - Get-CsActiveUserReport, das Informationen zur Anzahl der aktiven Benutzer bereitstellt (Benutzer, die sich bei Skype for Business Online angemeldet haben und an mindestens einer Konferenz oder einer Peer-to-Peer-Kommunikationssitzung teilgenommen haben).

  - Get-CsAVConferenceTimeReport, das Informationen über den Zeitraum (in Minuten), den Benutzer in Audio/Video-Konferenzen verbracht haben, bereitstellt.

  - Get-CsConferenceReport, das Informationen über die Anzahl und den Typ von Konferenzen bereitstellt, an denen Benutzer teilgenommen haben.

  - Get-CsP2PAVTimeReport, das Informationen über den Zeitraum (in Minuten), den Benutzer in Peer-to-Peer-Sitzungen mit Audio-und/oder Videodaten verbracht haben.

  - Get-CsP2PSessionReport, das Informationen über die Anzahl und den Typ von Peer-zu-Peer-Sitzungen bereitstellt, an denen Benutzer teilgenommen haben.

Die meisten Administratoren verwenden die Berichte, die im Microsoft 365 Admin Center zur Verfügung stehen: Diese Berichte werden nicht nur automatisch generiert, sondern bieten auch eine grafische Darstellung der Daten, die häufig einfacher zu interpretieren sind als die unformatierten Zahlenwerte, die von der Cmdlets für die Berichterstellung. Administratoren, die mit Windows PowerShell vertraut sind, können jedoch mithilfe der Cmdlets für die Berichterstellung Daten zurückgeben, die in den lync Online Berichten nicht leicht verfügbar sind. Beispielsweise werden mit den Cmdlets für die Berichterstellung Informationen zur Sitzungsdauer zurückgegeben (der Zeitraum in Minuten, in dem jede Sitzung dauerte). Einzelne Sitzungsdauer sind nicht verfügbar, wenn Sie die lync Online Berichte verwenden. Dementsprechend werden in den lync Online Berichten in der täglichen Ansicht nur Informationen für die vorhergehenden 14 Tage angezeigt. Wenn Sie die Tagessummen für einen anderen Tag (beispielsweise ein Datum aus vier Monaten) überprüfen möchten, können Sie dies mithilfe der Cmdlets für die Berichterstellung tun.

Administratoren sind möglicherweise auch an dem Artikel interessiert, der [Excel zum Abrufen von Office 365 Berichtsdaten](https://msdn.microsoft.com/library/dn781442.aspx)verwendet, in dem die Verwendung der OData-Datenabfrage Funktion in Microsoft Excel zum Erstellen eines benutzerdefinierten Office 365-Berichts erläutert wird. Benutzerdefinierte Berichte bieten Ihnen die Möglichkeit zu diktieren, welche Daten (und wie viele Daten) vom Office 365 Berichtsdienst zurückgegeben werden. Mit benutzerdefinierten Berichten können Sie auch solche Dinge tun, die angeben, wie die Daten sortiert und gruppiert werden sollen, und den Zugriff auf Informationen ermöglichen, die nicht im Admin Center angezeigt werden.

Administratoren mit Entwicklungshintergrund können mithilfe des Rest-Webdiensts Informationen abrufen, die nicht im Skype for Business Online Admin Center angezeigt werden. Der Rest-Dienst ähnelt dem SOAP-Dienst, da jede Technologie eine Möglichkeit bietet, XML-Daten zwischen einem Client und einem Server zu übertragen. Der Rest-Dienst verfügt jedoch über mindestens zwei Vorteile gegenüber dem SOAP-Dienst. Für einen übernimmt Rest XML-Datenübertragungen unter Verwendung eines standardisierten Formats, das als Atom-Veröffentlichungsformat bezeichnet wird. Im Gegensatz dazu verwendet SOAP ein nicht standardmäßiges Format beim Übertragen von Daten. Darüber hinaus kann Rest Daten über Netzwerke übertragen, die HTTP-Verben außer Get und Post blockieren.

<div>

## <a name="see-also"></a>Siehe auch


[Lync Online Berichterstellung](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Der Webdienst für die Office 365-Berichterstellung](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[Informationen zum Webdienst "Office 365-Berichterstellung"](https://msdn.microsoft.com/library/office/jj984321.aspx)  
[Die Cmdlets für die Exchange Online-Berichterstellung](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Verwenden von Excel zum Abrufen von Office 365-Berichterstellungsdaten](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

