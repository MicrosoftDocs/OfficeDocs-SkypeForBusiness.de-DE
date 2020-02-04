---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Suche von Verbundpartnern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Zu dem Zeitpunkt, zu dem Sie Ihre Edgeserver und den aktivierten Verbund für Ihre Organisation bereitgestellt haben, sollten Sie angeben, ob die automatische Ermittlung von Verbundpartner Domänen unterstützt werden soll. Verwenden Sie das in diesem Thema beschriebene Verfahren, um diese Konfiguration zu ändern.

<div>


> [!NOTE]  
> Im folgenden Verfahren wird davon ausgegangen, dass Sie die Föderation für Ihre Organisation bereits aktiviert haben. Details zum Aktivieren von Föderation finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A> in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>So aktivieren oder deaktivieren Sie die automatische Ermittlung von Verbunddomänen für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren oder deaktivieren Sie in der **Konfiguration der Access-Edge-Konfiguration**unter **Kommunikation mit Verbundbenutzern aktivieren**das Kontrollkästchen **Ermittlung der Partnerdomäne aktivieren** , um die automatische Ermittlung von Partnerdomänen zu aktivieren oder zu deaktivieren.

6.  Klicken Sie auf **Commit ausführen**.

Damit Verbundbenutzer mit Benutzern in ihrer lync Server-Bereitstellung zusammenarbeiten können, müssen Sie auch mindestens eine Richtlinie für den externen Zugriff konfiguriert haben, um den Verbundbenutzer Zugriff zu unterstützen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation. Details zum Steuern des Zugriffs für bestimmte Verbunddomänen finden Sie unter [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) und [Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in der Betriebsdokumentation.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern mithilfe von Windows PowerShell-Cmdlets

Die Ermittlung von Verbundpartnern kann mithilfe von Windows PowerShell und dem Cmdlet "csaccessedgeconfiguration nicht angeben" verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>So aktivieren Sie die Suche nach Verbundpartnern

  - Um die Suche nach Verbundpartnern zu aktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf true ($true). Beachten Sie, dass Sie das DNS-SRV-Routing aktivieren müssen, um diesen Eigenschaftswert zu ändern.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>So deaktivieren Sie die Ermittlung von Verbundpartnern

  - Um die Ermittlung von Verbundpartnern zu deaktivieren, setzen Sie den Wert der **EnablePartnerDiscovery** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

