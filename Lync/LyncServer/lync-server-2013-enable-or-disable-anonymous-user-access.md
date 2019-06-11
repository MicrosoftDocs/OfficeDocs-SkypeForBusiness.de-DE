---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d07bf27f5424f121c5dcf070f5231e2fd8c324f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Anonyme Benutzer sind Benutzer, die nicht über ein Benutzerkonto in den Active Directory-Domänendiensten Ihrer Organisation oder in einer unterstützten Föderationsdomäne verfügen, aber zur Remote Teilnahme an einer lokalen Konferenz eingeladen werden können. Durch das zulassen anonymer Teilnahme an Besprechungen können Sie anonyme Benutzer (also Benutzer, deren Identität nur über den Besprechungs-oder Konferenzschlüssel überprüft wird) aktivieren, um an Besprechungen teilzunehmen. Das Zulassen einer anonymen Teilnahme erfordert die Aktivierung für Ihre Organisation.

Wenn Sie den Zugriff von anonymen Benutzern später vorübergehend oder dauerhaft verhindern möchten, können Sie ihn für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt, um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren oder zu deaktivieren.

<div>


> [!NOTE]  
> Indem Sie den anonymen Benutzer Zugriff für Ihre Organisation aktivieren, geben Sie nur an, dass die Server, auf denen der Access Edge-Dienst ausgeführt wird, den Zugriff durch anonyme Benutzer unterstützen. Anonyme Benutzer können erst dann an Besprechungen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine konferenzrichtlinie konfiguriert und auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Die einzigen Benutzer, die anonyme Benutzer zu Besprechungen einladen können, sind diejenigen Benutzer, denen eine konferenzrichtlinie zugewiesen ist, die für die Unterstützung anonymer Benutzer konfiguriert ist. Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung der Einladung anonymer Benutzer finden Sie unter <A href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>So aktivieren oder deaktivieren Sie den anonymen Benutzer Zugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Access-Edge-Konfiguration**.

4.  Klicken Sie auf der Seite **Access Edge Configuration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in " **Access-Edge-Konfiguration bearbeiten**" eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** , um den anonymen Benutzer Zugriff für Ihre Organisation zu aktivieren.
    
      - Wenn Sie den anonymen Benutzer Zugriff für Ihre Organisation deaktivieren möchten, deaktivieren Sie das Kontrollkästchen **Kommunikation mit anonymen Benutzern aktivieren** .

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Zugriffs auf anonyme Benutzer mithilfe von Windows PowerShell-Cmdlets

Sie können den anonymen Benutzer Zugriff mithilfe von Windows PowerShell und dem Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " verwalten. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-anonymous-user-access"></a>So aktivieren Sie den anonymen Benutzer Zugriff

  - Um den anonymen Benutzer Zugriff zu aktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf true ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>So deaktivieren Sie den anonymen Benutzer Zugriff

  - Um den anonymen Benutzer Zugriff zu deaktivieren, setzen Sie den Wert der **AllowAnonymousUsers** -Eigenschaft auf false ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Referenz für konferenzrichtlinieneinstellungen für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

