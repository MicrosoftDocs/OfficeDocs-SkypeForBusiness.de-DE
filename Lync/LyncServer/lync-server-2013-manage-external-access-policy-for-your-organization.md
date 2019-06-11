---
title: 'Lync Server 2013: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Nachdem Sie einen oder mehrere Edge-Server bereitgestellt haben, müssen Sie die Typen des externen Zugriffs aktivieren, die für Ihre Organisation unterstützt werden.

Standardmäßig sind keine Richtlinien zur Unterstützung des Zugriffs externer Benutzer, einschließlich des Remotebenutzerzugriffs, des Zugriffs auf den Verbundbenutzer konfiguriert, auch wenn Sie die Unterstützung für den externen Benutzer Zugriff für Ihre Organisation bereits aktiviert haben. Um die Verwendung des Zugriffs auf externe Benutzer zu steuern, müssen Sie eine oder mehrere Richtlinien konfigurieren und den Typ des für jede Richtlinie unterstützten externen Benutzerzugriffs angeben. Die folgenden Richtlinienbereiche stehen für die Erstellung und Konfiguration zur Verfügung. Standardmäßig wird die globale Richtlinie erstellt, kann aber nicht gelöscht werden.

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind keine Optionen für den externen Benutzer Zugriff in der globalen Richtlinie aktiviert. Zur Unterstützung des Zugriffs externer Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützt werden. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, aber Website Richtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, werden Sie nicht entfernt. Stattdessen setzen Sie Sie auf die Standardeinstellung zurück.

  - **Website Richtlinie**   Sie können eine oder mehrere Website Richtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff externer Benutzer auf bestimmte Websites zu begrenzen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, geben Sie möglicherweise eine Website Richtlinie an, die den Remotebenutzerzugriff für eine bestimmte Website deaktiviert. Standardmäßig wird eine Website Richtlinie auf alle Benutzer dieser Website angewendet, aber Sie können einem Benutzer eine Benutzerrichtlinie zuweisen, um die Website Richtlinieneinstellung zu überschreiben.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer zu begrenzen. Die Konfiguration in der Benutzerrichtlinie überschreibt die globale und die Website Richtlinie, jedoch nur für bestimmte Benutzer, denen die Benutzerrichtlinie zugewiesen ist. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und der Website Richtlinie aktivieren, geben Sie möglicherweise eine Benutzerrichtlinie an, die den Zugriff durch Remotebenutzer deaktiviert und diese Benutzerrichtlinie dann bestimmten Benutzern zuweist. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie Sie auf einen oder mehrere Benutzer anwenden, bevor Sie wirksam wird.

<div>


> [!IMPORTANT]  
> Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.



</div>

Zu diesen Optionen gehören die folgenden Typen von externem Zugriff:

  - **Aktivieren der Kommunikation mit Verbundbenutzern**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Partnerdomänen für Föderationen unterstützen möchten. Diese Einstellung konfiguriert die Möglichkeit für Benutzer, mit anderen SIP-Verbunddomänen sowie gehosteten Anbietern wie Microsoft Office 365 zu kommunizieren. Wenn Sie diese Einstellung auswählen, können Sie die Option zum Zulassen der Kommunikation mit XMPP-Verbunddomänen auswählen.
    
    Optional können Sie die Option **Kommunikation mit XMPP-Verbundpartnern aktivieren** auswählen, wenn Sie zuerst **Kommunikation mit Verbundbenutzern aktivieren**auswählen. Die XMPP-Föderation ist eine Föderation mit Organisationen, die das Extensible Messaging and Presence Protocol (XMPP) verwenden.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die XMPP-Föderation aktivieren, müssen Sie auch den <STRONG>XMPP-Verbund</STRONG> im Bereich "Edge-Pools-Konfiguration" des Topologie-Generators bereitstellen. Bei der Konfiguration für XMPP Federation wird ein XMPP-Proxy auf dem Edgeserver und ein XMPP-Gateway auf dem Front-End-Server bereitgestellt.

    
    </div>

  - **Aktivieren der Kommunikation mit Remotebenutzern**   aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server über das Internet herstellen können.

  - **Aktivieren der Kommunikation mit öffentlichen Benutzern**   aktivieren Sie diese Option, wenn interne Benutzer in der Lage sein sollen, mit öffentlichen Chat Dienstanbieter-Kontakten zu kommunizieren, wie Sie von\!Windows Live, Yahoo und America Online (AOL) bereitgestellt werden.
    
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

<div>


> [!NOTE]  
> Neben der Unterstützung für den Zugriff durch externe Benutzer müssen Sie auch Richtlinien konfigurieren, um die Verwendung des Zugriffs externer Benutzer in Ihrer Organisation zu steuern, bevor Benutzer Zugriff auf externe Benutzer erhalten. Details zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>.



</div>

**So zeigen Sie die Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets an**

  - Sie können die Richtlinien für den externen Zugriff mit der lync Server-Verwaltungsshell und dem Cmdlet **Get-CsExternalAccessPolicy** anzeigen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.
    
    Wenn Sie Informationen zu allen Ihren externen Zugriffsrichtlinien anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsExternalAccessPolicy
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Zurücksetzen oder Löschen von Richtlinien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

