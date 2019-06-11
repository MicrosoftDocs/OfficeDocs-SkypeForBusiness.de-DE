---
title: 'Lync Server 2013: Löschen vorhandener Registrierungs Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9fe0ee46ff823a5184ee79f3b06bb02bb68115d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Löschen vorhandener Registrierungs Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Registrierungsstelle zu löschen.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>So löschen Sie Registrierungsstellenkonfigurationseinstellungen

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierungsstelle**.

4.  Geben Sie auf der Seite **Registrierungsstelle** in das Suchfeld den vollständigen oder teilweisen Namen der Registrierungsstelle ein, die Sie löschen möchten.

5.  Klicken Sie in der Liste auf die gewünschte Registrierungsstelle, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie anschließend auf **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Registrierungsstellen-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen der Registrierungsstelle mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsProxyConfiguration** löschen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>So entfernen Sie eine bestimmte Gruppe mit Registrierungsstellensicherheitseinstellungen

  - Mithilfe des folgenden Befehls werden die auf den Edgeserver „atl-edge-011.litwareinc.com“ angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die auf den Standortbereich angewendet werden

  - Mithilfe des folgenden Befehls werden alle auf den Registrierungsstellendienst angewendeten Sicherheitseinstellungen für die Registrierungsstelle entfernt:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierungsstelle, die die NTLM-Authentifizierung zulassen

  - Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierungsstelle gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

