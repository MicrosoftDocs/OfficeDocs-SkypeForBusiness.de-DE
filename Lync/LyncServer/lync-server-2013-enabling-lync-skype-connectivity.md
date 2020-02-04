---
title: 'Lync Server 2013: Aktivieren der Lync-Skype-Konnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Aktivieren der Lync-Skype-Konnektivität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-16_

Nachdem Sie die Bereitstellungsanforderung übermittelt haben, können Sie sich auf die lync Server-Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren der lync-Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der lync Server-Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren von externem Zugriff für lync Server finden Sie unter [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Um die lync Server-Umgebung für lync-Skype-Konnektivität vorzubereiten, muss der lync Server-Administrator die folgenden drei Aufgaben ausführen:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Konfigurieren des Partnerverbunds und der PIC

Föderation ist erforderlich, um Skype-Benutzern die Kommunikation mit lync-Benutzern in Ihrer Organisation zu ermöglichen. PIC (Public Instant Messaging Connectivity) ist eine Klasse des Verbandes und muss so konfiguriert sein, dass Ihre lync-Nutzer mit Skype-Nutzern kommunizieren können. Föderation und PIC werden mithilfe der lync Server-Systemsteuerung konfiguriert (siehe unten).

![PIC wird angezeigt](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC wird angezeigt")

<div>


> [!IMPORTANT]  
> Der PIC-Partnerverbund wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Zu den unterstützten Plattformen für die PIC-Föderation gehören lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Benutzerzugriffs im Partnerverbund

Mithilfe der lync Server-Systemsteuerung muss ein Administrator mindestens eine Richtlinie für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.

![Richtlinien](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Richtlinien")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Konfigurieren der Skype PIC-Anbieter Einstellung für lync

Mithilfe der lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.

<div>


> [!NOTE]  
> Benutzer der Dienstanbieter für öffentliche Instant Messaging-Konnektivität (PIC) können nicht an Chat-oder Audio-oder Videokonferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) konfiguriert haben, um die Konnektivität öffentlicher Chats zu unterstützen.



</div>

1.  Informationen zum Konfigurieren von Verbund und PIC finden Sie unter "aktivieren oder Deaktivieren von [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)Verbund-und öffentlichen Chat Verbindungen" unter.

2.  Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern finden Sie unter "Konfigurieren von Richt [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)Linien zum Steuern des Zugriffs öffentlicher Benutzer" unter.

**So bearbeiten Sie einen vorhandenen Messenger oder Skype PIC-Anbieter und konfigurieren ihn für Skype**

1.  Öffnen Sie auf einem lync Server-Front-End-Server die lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden beiden Befehle aus:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie nicht bereits über einen PIC-Anbieter in Ihrer Umgebung verfügen und einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > In lync Server 2013 CU5 &amp; lync-Desktop Client in Office 2013 SP1 wurde die Situation verbessert, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "schmücken", um Sie zu identifizieren und an Skype weiterzuleiten (das Format von: User (contoso. com) @MSN. com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der im Dialogfeld „Skype-Kontakt hinzufügen“ eingegebenen Benutzeradresse mit dem Parameter „NameDecorationRoutingDomain“ (der auf „msn.com“ festgelegt sein sollte), wenn die Domänen nicht im Parameter „NameDecorationExcludedDomainList“ enthalten sind (zurzeit werden „msn.com“, „live.com“, „Hotmail.com“ und „outlook.com“ unterstützt).

    
    </div>

3.  Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie sein Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Nutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Nutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [Verwenden der lync-Skype-Konnektivität in lync Server 2013 als Endbenutzer](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Skype-Kontakt hinzufügen](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype-Kontakt hinzufügen")

4.  Detaillierte Informationen zum Ändern von gehosteten Anbietern finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)-Verbund Anbietern" unter.

Damit sind die Verwaltungsaufgaben abgeschlossen, die auf dem Server durchgeführt werden müssen. Sie sind jetzt für die lync-Skype-Konnektivität eingerichtet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

