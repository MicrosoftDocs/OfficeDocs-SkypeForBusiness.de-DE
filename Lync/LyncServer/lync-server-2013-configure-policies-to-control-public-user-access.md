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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Mit der öffentlichen Instant Messaging-Konnektivität (im) können Benutzer in Ihrer Organisation Chatnachrichten verwenden, um mit Benutzern der Chat Dienste zu kommunizieren, die von öffentlichen Chat Dienstanbietern bereitgestellt werden,\!einschließlich des Windows Live-Netzwerks von Internet Diensten, Yahoo und AOL. Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob öffentliche Benutzer mit internen lync Server-Benutzern zusammenarbeiten können. Die öffentliche Instant Messaging-Konnektivität ist ein hinzugefügtes Feature, das auf der Konfiguration Ihrer Bereitstellung und der Benutzer basiert. Sie hängt auch von der Bereitstellung des Diensts beim öffentlichen Chat Dienstanbieter ab. Informationen dazu, wie Sie Ihre Bereitstellung für die Verwendung der öffentlichen Anbieter bereitstellen können, finden Sie im Leitfaden zu den öffentlichen im-Konnektivität für Microsoft lync Server, Office Communications Server und Live Communications Server.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>



</div>

Verwenden Sie den folgenden Link, um auf die Bereitstellung der Microsoft lync Server Public im Connectivity-Bereitstellungswebsite zuzugreifen:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

Wenn Sie den Zugriff durch öffentliche Benutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren. Details zu den Richtlinientypen, die Sie konfigurieren können, finden Sie unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in der Bereitstellungsdokumentation oder in der Planungsdokumentation. Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

Im Fall von Chat-Einladungen hängt die Antwort von der Client Software ab. Die Anforderung wird akzeptiert, es sei denn, externe Absender werden explizit durch eine vom Benutzer konfigurierte Regel blockiert (also die Einstellungen in den Client- **Allow** -und- **Block** Listen). Darüber hinaus können Chat-Einladungen blockiert werden, wenn ein Benutzer wählt, Alle Chatnachrichten von Benutzern zu blockieren, die nicht in der **Zulassungs** Liste aufgeführt sind.

<div>


> [!NOTE]  
> Sie können Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer konfigurieren, auch wenn Sie die Föderation für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Verbund für Ihre Organisation aktiviert ist. Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Details zum Angeben von öffentlichen Benutzern, die sich bei lync Server anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.



</div>

Gehen Sie wie folgt vor, um eine Richtlinie zum unterstützen des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Chat Anbieter zu konfigurieren.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Zugriffs durch öffentliche Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:
    
      - Wenn Sie die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnablePublicUsers** für eine Benutzerrichtlinie, die die Kommunikation für öffentliche Benutzer aktiviert).
    
      - Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff öffentlicher Benutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Wenn Sie den Zugriff durch öffentliche Benutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Verbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die in der Lage sein sollen, mit öffentlichen Benutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

