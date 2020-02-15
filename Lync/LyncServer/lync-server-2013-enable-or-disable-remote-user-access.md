---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Remotebenutzerzugriffs'
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
ms.openlocfilehash: c673295f2344d2ca3ca853f76775bbae47a74328
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Remote Benutzer sind Benutzer in Ihrer Organisation, die über eine persistente Active Directory Identität innerhalb der Organisation verfügen. Remote Benutzer melden sich häufig über ein virtuelles privates Netzwerk (VPN) bei lync Server von außerhalb Ihres Netzwerks an, wenn Sie nicht mit dem Netzwerk Ihrer Organisation verbunden sind. Zu den Remotebenutzern gehören Mitarbeiter, die zu Hause oder unterwegs arbeiten, und andere Remotemitarbeiter, beispielsweise vertrauenswürdige Anbieter, denen Enterprise-Anmeldeinformationen erteilt wurden. Wenn Sie den Remotebenutzerzugriff für Remotebenutzer aktivieren, werden unterstützte Remotebenutzer über das Internet verbunden und müssen nicht über ein VPN eine Verbindung herstellen, um mit internen Benutzern mit lync Server zusammenzuarbeiten.

Um den Zugriff durch Remotebenutzer zu unterstützen, müssen Sie den Remotebenutzerzugriff aktivieren. Wenn Sie den Remotebenutzerzugriff aktivieren, aktivieren Sie ihn für die gesamte Organisation. Wenn Sie später den Remotebenutzerzugriff vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den Zugriff durch Remotebenutzer für Ihre Organisation zu aktivieren oder zu deaktivieren.

<div>


> [!NOTE]  
> Aktivieren des Remotebenutzerzugriffs nur gibt an, dass Ihre Server mit dem Zugriffs-Edgedienst die Kommunikation mit Remotebenutzern unterstützen, Remotebenutzer können jedoch nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch unter mindestens eine Richtlinie zum Verwalten der Verwendung des Remotebenutzerzugriffs. Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft. Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Verwendung des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configure Policies to Control Remote User Access in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den Zugriff durch Remotebenutzer für Ihre Organisation

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf Partner **Verbund und externer Zugriff**, und klicken Sie dann auf **Zugriffs-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Konfiguration für Zugriffsedge bearbeiten** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Remotebenutzerzugriff aktivieren** , um den Zugriff durch Remotebenutzer für Ihre Organisation zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Remotebenutzer sich bei ihren Servern anmelden können, auf denen lync Server ausführt, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfigurieren, um den Zugriff durch Remotebenutzer zu unterstützen. Ausführliche Informationen finden Sie unter [configure Policies to Control Remote User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Remote Benutzerzugriffs mithilfe von Windows PowerShell-Cmdlets

Der Remote Benutzer Zugriff kann mit Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-remote-user-access"></a>So aktivieren Sie den Remotebenutzerzugriff

  - Legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf true ($true) fest, um den Remotebenutzerzugriff zu aktivieren:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>So deaktivieren Sie den Remotebenutzerzugriff

  - Wenn Sie den Remotebenutzerzugriff deaktivieren möchten, legen Sie den Wert der **AllowOutsideUsers** -Eigenschaft auf false ($false) fest:
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

