---
title: Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0715a7fc0dd9ab81d84fd996d5b87682af3f69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Zu dem Zeitpunkt, zu dem Sie die Edgeserver und den aktivierten Partnerverbund für Ihre Organisation bereitgestellt haben, sollten Sie angegeben haben, ob der Haftungsausschluss für die Archivierung automatisch an Verbundpartner gesendet werden soll. Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Haftungsausschlusses für die Archivierung aktivieren. Verwenden Sie das Verfahren in diesem Thema, um diese Konfiguration zu ändern.

<div>


> [!NOTE]
> Im folgenden Verfahren wird vorausgesetzt, dass Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben. Ausführliche Informationen zum Aktivieren des Verbund finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden eines Archivierungs Disclaimers an Verbundpartner

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Registerkarte **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren oder deaktivieren Sie im Abschnitt **Bearbeiten der Zugriffs-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Archivierungs Haftungsausschluss an Verbundpartner senden** , um das automatische Senden des Haftungsausschlusses für die Archivierung zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Verbundbenutzer konfiguriert haben. Ausführliche Informationen finden Sie unter [Manage XMPP Federated Partners in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Ausführliche Informationen zum Steuern des Zugriffs auf bestimmte Verbunddomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungs Disclaimers mithilfe von Windows PowerShell-Cmdlets

Die Verwendung des Haftungsausschlusses für die Archivierung kann mithilfe von Windows PowerShell und dem Cmdlet "Cmdlet festlegen" verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>So aktivieren Sie den Haftungsausschluss für Archivierung

  - Um den Haftungsausschluss für die Archivierung zu aktivieren, legen Sie den Wert der **EnableArchivingDisclaimer** -Eigenschaft auf true ($true) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>So deaktivieren Sie den Haftungsausschluss für Archivierung

  - Wenn Sie den Haftungsausschluss für die Archivierung deaktivieren möchten, legen Sie den Wert der **EnableArchivingDisclaimer** -Eigenschaft auf false ($false) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

