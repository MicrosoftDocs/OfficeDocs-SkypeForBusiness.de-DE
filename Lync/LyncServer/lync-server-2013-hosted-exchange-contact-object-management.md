---
title: 'Lync Server 2013: Kontaktobjektverwaltung für gehostete Exchange-Dienste'
TOCTitle: Kontaktobjektverwaltung für gehostete Exchange-Dienste
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412978(v=OCS.15)
ms:contentKeyID: 49295825
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kontaktobjektverwaltung für gehostete Exchange-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Sie müssen für jede Nummer einer automatischen Telefonzentrale und für jede Teilnehmerzugriffsnummer in Ihrer standortübergreifenden Bereitstellung ein Kontaktobjekt erstellen.

Bei der Integration in gehostete Exchange UM-Dienste kann kann "ocsumutil.exe" nicht zur Verwaltung von Kontaktobjekten verwendet werden, da das Integrationsprogramm von Active Directory-Einstellungen für Exchange UM abhängt. In einer standortübergreifenden Bereitstellung sind Lync Server 2013 und der gehostete Exchange UM-Dienst in getrennten Gesamtstrukturen ohne gegenseitige Vertrauensstellung installiert. Aus Sicherheitsgründen erhalten Lync Server 2013-Administratoren keinen direkten Zugriff auf die Active Directory-Einstellungen für Exchange UM. Daher bietet Lync Server 2013 ein anderes Modell zur Verwaltung von Kontaktobjekten in einem *freigegebenen SIP-Adressraum* , auf den sowohl Lync Server 2013 als auch der gehostete Exchange UM-Dienst zugreifen können.

## Workflow für gehostete Kontaktobjekte

Der Administrator für gehostete Exchange-Mandanten verwaltet Kontaktobjekte anhand folgender allgemeiner Schritte:

1.  Der Exchange-Administrator fordert Rufnummern für den Exchange UM-Teilnehmerzugriff und Kontaktobjekte für die automatische Telefonzentrale an.

2.  Der Lync Server 2013-Administrator erstellt ein Kontaktobjekt für jede Rufnummer und weist jedem Kontaktobjekt eine Richtlinie für gehostete Voicemail zu.

3.  Der Lync Server 2013-Administrator sendet dem Exchange-Administrator die Rufnummern.

4.  Der Exchange-Administrator weist die Rufnummern den entsprechenden Exchange UM-Wähleinstellungen für die automatische Telefonzentrale und den Teilnehmerzugriff zu.


> [!NOTE]
> Im Gegensatz zu lokalen Bereitstellungen müssen keine Lync Server 2013-Wähleinstellungen für die Kontaktobjekte konfiguriert werden.



## Konfigurieren von gehosteten Kontaktobjekten


> [!NOTE]
> Bevor Lync Server 2013-Kontaktobjekte für gehostete Exchange UM-Dienste aktiviert werden können, muss eine Richtlinie für gehostete Voicemail erstellt werden, die auf diese Objekte angewendet werden kann. Diese Richtlinie kann auf globaler, Standort- oder Benutzerebene eingerichtet werden, vorausgesetzt, sie lässt sich auf das Kontaktobjekt anwenden, das Sie aktivieren möchten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in Lync Server 2013</A>.



Zur Konfiguration von Kontaktobjekten für die automatische Telefonzentrale und den Teilnehmerzugriff in einer standortübergreifenden Bereitstellung müssen Sie folgende Cmdlets verwenden:

  - **New-CsExUmContact** erstellt ein neues Kontaktobjekt für gehostete UM-Dienste.

  - **Set-CsExUmContact** ändert ein vorhandenes Kontaktobjekt für den Einsatz gehosteter Exchange UM-Dienste.

Im folgenden Beispiel wird ein Kontaktobjekt für eine automatische Telefonzentrale erstellt:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

In diesem Beispiel wird ein neues Exchange UM-Kontaktobjekt mit der SIP-Adresse "sip:exumaa1@fabrikam.com" erstellt. Der Name des Pools, in dem der Lync Server 2013-Registrierungsdienst ausgeführt wird, lautet "RedmondPool.litwareinc.com". Diese Informationen werden in der Active Directory-Organisationseinheit "OU=ExUmContacts,DC=litwareinc,DC=com" gespeichert. Die Rufnummer des Kontaktobjekts lautet 2065554567. Der optionale Parameter "-AutoAttendant $True" gibt an, dass es sich bei diesem Objekt um ein Kontaktobjekt für eine automatische Telefonzentrale handelt. Wenn der Parameter "-AutoAttendant" auf "False" gesetzt wird (dies ist die Standardeinstellung), handelt es sich um ein Kontaktobjekt für den Teilnehmerzugriff.

Ausführliche Informationen zu den Cmdlets "New-CsExUmContact" und "Set-CsExUmContact" finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

