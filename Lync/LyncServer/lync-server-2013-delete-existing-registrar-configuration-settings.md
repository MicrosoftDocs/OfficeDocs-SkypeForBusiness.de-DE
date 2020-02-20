---
title: 'Lync Server 2013: Löschen vorhandener Registrierungsstellen-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f127efa6e2cab04434dd8de6e541897d50483f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Löschen vorhandener Registrierungsstellen-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Registrierung zu löschen.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>So löschen Sie Registrierungs Konfigurationseinstellungen

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Registrierung**.

4.  Geben Sie auf der Seite **Registrierung** im Suchfeld Teile oder den vollständigen Namen der Registrierung ein, die Sie löschen möchten.

5.  Klicken Sie in der Liste auf die gewünschte Registrierung, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Registrierungsstellen-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Registrierungsstellen-Konfigurationseinstellungen mit Windows PowerShell und dem Cmdlet **Remove-CsProxyConfiguration** löschen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>So entfernen Sie eine bestimmte Gruppe mit Registrierungssicherheitseinstellungen

  - Mithilfe des folgenden Befehls werden die auf den Edgeserver "atl-edge-011.litwareinc.com" angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die auf Standortebene angewendet werden

  - Mithilfe des folgenden Befehls werden alle auf den Registrierungsdienst angewendeten Sicherheitseinstellungen für die Registrierung entfernt:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>So entfernen Sie alle Sicherheitseinstellungen für die Registrierung, die die NTLM-Authentifizierung zulassen

  - Mithilfe des folgenden Befehls werden alle Sicherheitseinstellungen für die Registrierung gelöscht, die die Verwendung von NTLM für die Clientauthentifizierung zulassen:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

