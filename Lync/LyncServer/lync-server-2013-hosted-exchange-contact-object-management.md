---
title: 'Lync Server 2013: Verwaltung von gehosteten Exchange-Kontaktobjekten'
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
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Hosted Exchange-Kontaktobjekt Verwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

Sie müssen ein Kontaktobjekt für jede Telefonzentrale und Teilnehmerzugriffsnummer in Ihrer standortübergreifenden Bereitstellung konfigurieren.

Für die Integration in gehostete Exchange um kann OCSUMUtil. exe nicht zum Verwalten von Kontaktobjekten verwendet werden, da dies von Active Directory Exchange um Einstellungen abhängt. In einer standortübergreifenden Bereitstellung werden lync Server 2013 und gehostete Exchange um in getrennten Gesamtstrukturen installiert, ohne dass diese vertrauenswürdig sind. Aus Sicherheitsgründen haben lync Server 2013 Administratoren keinen direkten Zugriff auf Exchange um Active Directory Einstellungen. Lync Server 2013 bietet daher ein anderes Modell für die Verwaltung von Kontaktobjekten in einem *freigegebenen SIP-Adressraum* , auf den sowohl lync Server 2013 als auch der gehostete Exchange um Dienst zugreifen können.

<div>

## <a name="hosted-contact-object-workflow"></a>Gehosteter Kontaktobjekt Workflow

Im folgenden finden Sie die allgemeinen Schritte zum Verwalten von Kontaktobjekten mit dem gehosteten Exchange-mandantenadministrator:

1.  Der Exchange-Administrator fordert Telefonnummern für die Exchange um Teilnehmerzugriffs und die Kontaktobjekte der automatischen Telefonzentrale an.

2.  Der lync Server 2013 Administrator erstellt ein Contact-Objekt für jede Telefonnummer und weist jedem Kontaktobjekt eine Richtlinie für gehostete Voicemail zu.

3.  Der lync Server 2013 Administrator stellt die Telefonnummern dem Exchange-Administrator zur Verfügung.

4.  Der Exchange-Administrator weist die Telefonnummern geeigneten Exchange UM Wähleinstellungen für automatische Telefonzentralen und Teilnehmerzugriff zu.

<div>


> [!NOTE]  
> Es ist nicht erforderlich, für die Kontaktobjekte lync Server 2013 Wählplaneinstellungen zu konfigurieren, wie dies bei lokalen Bereitstellungen der Falle ist.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Konfigurieren von gehosteten Kontaktobjekten

<div>


> [!NOTE]  
> Bevor lync Server 2013 Contact-Objekte für gehostete Exchange um aktiviert werden können, muss eine Richtlinie für gehostete Voicemail, die für Sie gilt, bereitgestellt werden. Die Richtlinie kann global, auf Standort-oder Benutzerebene verwendet werden, solange Sie auf das Kontaktobjekt angewendet wird, das Sie aktivieren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted Voice Mail Policies in lync Server 2013</A>.



</div>

Sie müssen die folgenden Cmdlets verwenden, um gehostete Kontaktobjekte für die automatische Telefonzentrale und den Teilnehmerzugriff in einer standortübergreifenden Bereitstellung zu konfigurieren:

  - **New-CsExUmContact** erstellt ein neues Kontaktobjekt für gehostete um.

  - Mit der **CsExUmContact-Einstellung** wird ein vorhandenes Contact-Objekt für gehostete Exchange um geändert.

Im folgenden Beispiel wird ein Contact-Objekt der automatischen Telefonzentrale erstellt:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

In diesem Beispiel wird ein neues Exchange um Contact-Objekt mit der SIP-Adresse SIP:exumaa1@fabrikam.com erstellt. Der Name des Pools, in dem der lync Server 2013 Registrierungsdienst aktiv ist, ist RedmondPool.litwareinc.com. Die Active Directory Organisationseinheit, in der diese Informationen gespeichert werden, ist ou = ExUmContacts, DC = litwareinc, DC = com. Die Telefonnummer des Kontaktobjekts lautet 2065554567. Der Parameter optional-autoattend $true gibt an, dass es sich bei diesem Objekt um ein Kontaktobjekt der automatischen Telefonzentrale handelt. Wenn Sie den-autoattender-Parameter auf "false" festlegen (Standardeinstellung), wird ein Kontaktobjekt des Teilnehmerzugriffs angegeben.

Ausführliche Informationen zu den Cmdlets New-CsExUmContact und CsExUmContact finden Sie in der Dokumentation zum lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

