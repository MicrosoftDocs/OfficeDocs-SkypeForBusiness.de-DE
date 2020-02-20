---
title: 'Lync Server 2013: Aktivieren der lync-Skype-Konnektivität'
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
ms.openlocfilehash: 4bb14153739c5f29e88044eae89a1322b046a0a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Aktivieren von lync-Skype-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-16_

Nachdem Sie die Bereitstellung angefordert haben, können Sie sich auf die lync Server Umgebung und die administrativen Aufgaben konzentrieren, die zum Konfigurieren der lync-Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der lync Server Administrator lync Server bereitgestellt und den externen Zugriff konfiguriert hat. Weitere Informationen zum Konfigurieren des externen Zugriffs für lync Server finden Sie unter [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Um die lync Server Umgebung für die lync-Skype-Konnektivität vorzubereiten, muss der lync Server-Administrator die folgenden drei Aufgaben ausführen:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Konfigurieren von Partnerverbund und PIC

Partnerverbund ist erforderlich, damit Skype-Benutzer mit lync-Benutzern in Ihrer Organisation kommunizieren können. Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre lync-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe der lync Server-Systemsteuerung, unten dargestellt, konfiguriert.

![Anzeigen von PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Anzeigen von PIC")

<div>


> [!IMPORTANT]  
> PIC Federation wird von Live Communication Server 2005 SP1 oder Office Communications Server 2007 nicht mehr unterstützt. Die unterstützten Plattformen für den PIC-Verbund umfassen lync Server 2013, lync Server 2010 und Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer

Mit dem lync Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen lync Server-Benutzern zusammenarbeiten können.

![Richtlinien](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Richtlinien")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Konfigurieren der Skype PIC-Anbieter Einstellung für lync

Mit dem lync Server-Verwaltungsshell muss ein Administrator die lync-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird.

<div>


> [!NOTE]  
> Benutzer von PIC-Dienstanbietern (Public Instant Messaging Connectivity) können nicht an Chat-oder Audio-oder Videokonferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben.



</div>

1.  Informationen zum Konfigurieren von Partnerverbund und PIC finden Sie unter "aktivieren oder Deaktivieren von [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063)Verbund-und öffentlichen Chat Verbindungen" unter.

2.  Informationen zum Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer finden Sie unter "configure Policies [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064)to Control Public User Access" unter.

**So bearbeiten Sie einen vorhandenen Messenger-oder Skype PIC-Anbieter und konfigurieren ihn für Skype**

1.  Öffnen Sie in einer lync Server Front-End-Server die lync Server-Verwaltungsshell.

2.  Führen Sie die folgenden zwei Befehle aus:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Wenn in Ihrer Umgebung noch kein PIC-Anbieter vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet <STRONG>Remove-CsPublicProvider</STRONG> nicht ausführen.

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > In lync Server 2013 CU5 &amp; lync-Desktop-Client in Office 2013 SP1 hinzugefügt, verbessern NameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "dekorieren", um diese zu identifizieren und an Skype weiterzuleiten (das Format: User (contoso. com) @MSN. com). Durch diese neuen Einstellungen wird die automatische Formatierung der Adresse eingegeben, die der Benutzer im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (der auf MSN.com festgelegt werden sollte) eingeben kann, wenn er die Domänen in der NameDecorationExcludedDomainList nicht enthält ( Wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen.

    
    </div>

3.  Von einem lync-Client aus können Sie nun Skype als PIC-Anbieter auswählen und einen Skype-Client hinzufügen, indem Sie Ihr Microsoft-Konto angeben. Darüber hinaus kann ein Skype-Benutzer, der sich mit seinem Microsoft-Konto zusammengeführt und angemeldet hat, Kontaktanfragen an lync-Benutzer senden. Weitere Informationen zu Microsoft-Konten finden Sie unter [Was ist ein Microsoft-Konto?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Weitere Informationen zum Hinzufügen von Clients zu lync finden Sie unter [using lync-Skype Connectivity in lync Server 2013 as a End User](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Skype-Kontakt hinzufügen](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype-Kontakt hinzufügen")

4.  Ausführliche Informationen zum Ändern gehosteter Anbieter finden Sie unter "erstellen oder Bearbeiten von gehosteten SIP- [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)Verbund Anbietern" unter.

Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind jetzt für die lync-Skype-Konnektivität eingerichtet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

