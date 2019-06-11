---
title: Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9364f3562c837b949ef589fc7c5cbd2bc4a2b4cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angegeben haben, ob die Archivierungs Verzicht automatisch an Verbundpartner gesendet werden soll. Wenn Sie die externe Kommunikation archivieren, sollten Sie das Senden eines Archivierungs Verzichts aktivieren. Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.

<div>


> [!NOTE]
> Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben. Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>So aktivieren oder deaktivieren Sie das Senden einer Archivierungs Klausel an verbundene Partner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Registerkarte **Zugriffs-Edgekonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und dann auf **Details einblenden**.

5.  Aktivieren oder deaktivieren Sie in " **Access-Edge-Konfiguration bearbeiten**" unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Archivierungs Ausschluss an verbundene Partner senden** , um das automatische Senden der Archivierung zu aktivieren oder zu deaktivieren. Haftungsausschluss.

6.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in ihrer lync Server 2013-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Details zum Steuern des Zugriffs auf bestimmte Föderationsdomänen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur Betriebsanleitung.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Archivierungs Verzichts mithilfe von Windows PowerShell-Cmdlets

Die Verwendung des Haftungsausschlusses für die Archivierung kann mithilfe von Windows PowerShell und dem Cmdlet "Satz-csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>So aktivieren Sie den Archivierungs Ausschluss

  - Zum Aktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „True“ ($True) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>So deaktivieren Sie den Haftungsausschluss für Archivierung

  - Zum Deaktivieren des Archivierungshaftungsausschlusses legen Sie den Wert der Eigenschaft **EnableArchivingDisclaimer** auf „False“ ($False) fest:
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

