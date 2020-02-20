---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a6e5d94cef7c9f25bb1c4091a981603f66da82
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Verbindung mit öffentlichen Instant Messaging-Verbindungen ermöglicht Benutzern in Ihrer Organisation die Verwendung von Chat, um mit Benutzern von Chat Diensten zu kommunizieren, die von öffentlichen Sofortnachrichten-Dienstanbietern bereitgestellt werden,\!einschließlich des Windows Live-Netzwerks für Internet Dienste, Yahoo und AOL. Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob öffentliche Benutzer mit internen lync Server Benutzern zusammenarbeiten können. Die Verbindung mit öffentlichen Instant Messaging-Diensten ist ein zusätzliches Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert. Es hängt auch von der Einrichtung des Diensts beim öffentlichen Instant Messaging-Anbieter ab. Informationen zum Bereitstellen der Bereitstellung für die Verwendung der öffentlichen Anbieter finden Sie im Leitfaden "Public im Connectivity Provisioning Guide for Microsoft lync Server, Office Communications Server und Live Communications Server".[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>



</div>

Verwenden Sie den folgenden Link, um auf die Microsoft lync Server-Website für die Konnektivität mit öffentlichen Instant Messaging-Diensten zuzugreifen:[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

Zum Steuern des Zugriffs durch öffentliche Benutzer können Sie Richtlinien auf globaler Ebene und Standort- und Benutzerebene konfigurieren. Ausführliche Informationen zu den Typen von Richtlinien, die Sie konfigurieren können, finden Sie unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in der Bereitstellungsdokumentation oder in der Planungsdokumentation. Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft. Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.

Im Fall von Sofortnachrichten-Einladungen hängt die Antwort von der Clientsoftware ab. Die Anforderung wird akzeptiert, sofern externe Absender nicht ausdrücklich durch eine vom Benutzer konfigurierte Regel (also Einstellungen in der **Zulassungs-** und **Blockierliste** des Benutzers) blockiert werden. Darüber hinaus können Sofortnachrichten-Einladungen blockiert werden, wenn ein Benutzer festlegt, dass alle Sofortnachrichten von Benutzern, die nicht in der **Zulassungsliste** enthalten sind, blockiert werden.

<div>


> [!NOTE]  
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch öffentliche Benutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Ausführliche Informationen zum Angeben von öffentlichen Benutzern, die sich bei lync Server anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.



</div>

Gehen Sie folgendermaßen vor, um eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Sofortnachrichtenanbieter zu konfigurieren.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch öffentliche Benutzer

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnablePublicUsers** für eine Benutzerrichtlinie, welche die Kommunikation für öffentliche Benutzer ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren**, um den Zugriff durch öffentliche Benutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit**.

Um den Zugriff durch öffentliche Benutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die mit öffentlichen Benutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [Zuweisen von benutzerspezifischen Richtlinien in lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

