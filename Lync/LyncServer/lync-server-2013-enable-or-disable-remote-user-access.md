---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 476cc3b90a2fdb603303789f3f9bfceb67766f5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei Remote Benutzern handelt es sich um Benutzer in Ihrer Organisation, die eine persistente Active Directory-Identität innerhalb der Organisation aufweisen. Remote Benutzer können sich häufig über ein virtuelles privates Netzwerk (VPN) bei lync Server von außerhalb Ihres Netzwerks anmelden, wenn diese nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Zu den Remotebenutzern gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, beispielsweise vertrauenswürdige Anbieter, denen Enterprise-Anmeldeinformationen gewährt wurden. Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden die unterstützten Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern mit lync Server zusammenzuarbeiten.

Wenn Sie den Zugriff durch Remotebenutzer unterstützen möchten, müssen Sie den Zugriff durch Remotebenutzer aktivieren. Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation. Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.

<div>


> [!NOTE]  
> Das Aktivieren des Remotebenutzerzugriffs gibt nur an, dass Ihre Server, auf denen der Access Edge-Dienst ausgeführt wird, die Kommunikation mit Remotebenutzern unterstützen, aber Remotebenutzer nicht an Instant Messaging (im) oder Konferenzen in Ihrer Organisation teilnehmen können, bis Sie auch die Konfiguration unter mindestens eine Richtlinie zum Verwalten der Verwendung von Remotebenutzerzugriff. Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt. Details zum Konfigurieren von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Remotebenutzerzugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Partnerverbund und externer Zugriff** und dann auf **Zugriffs-Edgekonfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Remotebenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Remotebenutzer sich bei ihren Servern mit lync Server anmelden können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Remote Benutzerzugriffs mithilfe von Windows PowerShell-Cmdlets

Der Remote Benutzer Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-remote-user-access"></a>So aktivieren Sie den Remotebenutzerzugriff

  - Um den Remotebenutzerzugriff zu aktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf true ($true) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>So deaktivieren Sie den Remotebenutzerzugriff

  - Um den Remotebenutzerzugriff zu deaktivieren, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf false ($false) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

