---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Sie konfigurieren eine oder mehrere Richtlinien für den externen Benutzer Zugriff, um zu steuern, ob Remotebenutzer mit internen lync Server-Benutzern zusammenarbeiten können. Wenn Sie den Zugriff durch Remotebenutzer steuern möchten, können Sie Richtlinien auf globaler, Website-und Benutzerebene konfigurieren. Website Richtlinien überschreiben die globale Richtlinie, und Benutzerrichtlinien überschreiben Website-und globale Richtlinien. Details zu den Richtlinientypen, die Sie konfigurieren können, finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

<div>


> [!NOTE]  
> Sie können Richtlinien konfigurieren, um den Remotebenutzerzugriff zu steuern, auch wenn Sie den Remotebenutzerzugriff für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien gelten jedoch nur, wenn der Remotebenutzerzugriff für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013</A>. Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Remotebenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind. Details zum Angeben von Benutzern, die sich bei lync Server von Remotestandorten aus anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013</A>.



</div>

Gehen Sie wie folgt vor, um jede Richtlinie für den externen Zugriff zu konfigurieren, die Sie zum Steuern des Remotebenutzerzugriffs verwenden möchten.

<div>


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie eine Richtlinie nur für die Kommunikation mit Remotebenutzern konfigurieren, aber jede Richtlinie, die Sie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, kann auch den Zugriff durch den Verbundbenutzer und den Zugriff auf öffentliche Benutzer konfigurieren. Details zum Konfigurieren von Richtlinien für die Unterstützung von Verbundbenutzern finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zum Steuern des Zugriffs auf den Verbundbenutzer in lync Server 2013</A>. Details zum Konfigurieren von Richtlinien für die Unterstützung öffentlicher Benutzer finden Sie unter <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>So konfigurieren Sie eine Richtlinie für den externen Zugriff zur Unterstützung des Remotebenutzerzugriffs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite " **externe Zugriffsrichtlinie** " eine der folgenden Aktionen aus:
    
      - Wenn Sie die globale Richtlinie für die Unterstützung des Remotebenutzerzugriffs konfigurieren möchten, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Website Richtlinie auf **neu**, und klicken Sie dann auf **Website Richtlinie**. Klicken Sie unter **Website auswählen**auf die entsprechende Website in der Liste, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in der **neuen Richtlinie für den externen Zugriff**im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableRemoteUsers** für eine Benutzerrichtlinie, die die Kommunikation für Remotebenutzer aktiviert).
    
      - Wenn Sie eine vorhandene Richtlinie ändern möchten, klicken Sie auf die entsprechende in der Tabelle aufgelistete Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Optional Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen für die Richtlinie unter **Beschreibung**an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Remotebenutzerzugriff für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Wenn Sie den Zugriff durch Remotebenutzer aktivieren möchten, müssen Sie auch die Unterstützung für den Zugriff durch Remotebenutzer in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

Wenn es sich um eine Benutzerrichtlinie handelt, müssen Sie die Richtlinie auch auf Benutzer anwenden, die eine Remoteverbindung herstellen können sollen. Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

