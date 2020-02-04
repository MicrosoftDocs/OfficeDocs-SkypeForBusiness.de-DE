---
title: 'Lync Server 2013: Kontaktobjektverwaltung für gehostete Exchange-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Kontaktobjektverwaltung für gehostete Exchange-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Sie müssen ein Kontaktobjekt für jede Nummer der automatischen Telefonzentrale und die Teilnehmerzugriffsnummer in Ihrer standortübergreifenden Bereitstellung konfigurieren.

Für die Integration in den Hosted Exchange um kann OCSUMUtil. exe nicht zum Verwalten von Kontaktobjekten verwendet werden, da dies von den Exchange um-Einstellungen von Active Directory abhängig ist. In einer standortübergreifenden Bereitstellung werden lync Server 2013 und gehostete Exchange um in getrennten Gesamtstrukturen installiert, ohne dass Sie vertrauenswürdig sind. Aus Sicherheitsgründen haben lync Server 2013-Administratoren keinen direkten Zugriff auf Exchange um-Active Directory-Einstellungen. Daher bietet lync Server 2013 ein anderes Modell für die Verwaltung von Kontaktobjekten in einem *freigegebenen SIP-Adressraum* , auf den sowohl lync Server 2013 als auch der gehostete Exchange um-Dienst zugreifen können.

<div>

## <a name="hosted-contact-object-workflow"></a>Workflow für gehostete Kontaktobjekte

Im folgenden finden Sie die allgemeinen Schritte für die Zusammenarbeit mit Ihrem Hosted Exchange-mandantenadministrator zum Verwalten von Kontaktobjekten:

1.  Der Exchange-Administrator fordert Telefonnummern für den Exchange um-Abonnenten Zugriff und die automatischen Telefonzentralen-Kontaktobjekte an.

2.  Der lync Server 2013-Administrator erstellt für jede Telefonnummer ein Kontaktobjekt und weist jedem Kontaktobjekt eine Richtlinie für gehostete Voicemail zu.

3.  Der lync Server 2013-Administrator stellt die Telefonnummern dem Exchange-Administrator zur Verfügung.

4.  Der Exchange-Administrator ordnet die Telefonnummern den entsprechenden Exchange um-Wählplänen für automatische Telefonzentralen und den Abonnenten Zugriff zu.

<div>


> [!NOTE]  
> Es ist nicht erforderlich, die Einstellungen für den Wählplan von lync Server 2013 für die Kontaktobjekte so zu konfigurieren, wie dies bei lokalen Bereitstellungen der Fall ist.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Konfigurieren von gehosteten Kontaktobjekten

<div>


> [!NOTE]  
> Bevor lync Server 2013-Kontaktobjekte für gehostete Exchange um aktiviert werden können, muss eine für Sie geltende gehostete Voicemail-Richtlinie bereitgestellt werden. Die Richtlinie kann globaler, Website ebener oder benutzerbezogener Bereich sein, sofern Sie auf das zu aktivierende Kontaktobjekt angewendet wird. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in lync Server 2013</A>.



</div>

Zum Konfigurieren der in einer lokalen Bereitstellung gehosteten Kontaktobjekte für die automatische Telefonzentrale und den Abonnenten Zugriff müssen Sie die folgenden Cmdlets verwenden:

  - **New-CsExUmContact** erstellt ein neues Kontaktobjekt für gehostete um.

  - Mit " **CsExUmContact** " wird ein vorhandenes Kontaktobjekt für gehostete Exchange um geändert.

Im folgenden Beispiel wird ein Kontaktobjekt der automatischen Telefonzentrale erstellt:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

In diesem Beispiel wird ein neues Exchange um-Kontaktobjekt mit der SIP-Adresse SIP:exumaa1@fabrikam.com erstellt. Der Name des Pools, in dem der lync Server 2013-Registrierungsdienst ausgeführt wird, lautet RedmondPool.litwareinc.com. Die Active Directory-Organisationseinheit, in der diese Informationen gespeichert werden, ist ou = ExUmContacts, DC = "litwareinc, DC = com. Die Telefonnummer des Kontaktobjekts ist 2065554567. Der Parameter optional – autoattende $true gibt an, dass dieses Objekt ein Kontaktobjekt der automatischen Telefonzentrale ist. Wenn der-autoattender-Parameter auf "false" festgelegt wird (der Standardwert), wird ein Kontaktobjekt des Teilnehmerzugriffs angegeben.

Ausführliche Informationen zu den Cmdlets New-CsExUmContact und CsExUmContact finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

