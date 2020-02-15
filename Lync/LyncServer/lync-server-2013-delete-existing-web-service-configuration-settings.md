---
title: 'Lync Server 2013: Löschen vorhandener Webdienst-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f54a83dc52a8dcdacd07c7d4464f46155d1860a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Löschen vorhandener Webdienst-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um Konfigurationseinstellungen für den Webdienst zu löschen.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>So löschen Sie Konfigurationseinstellungen für Webdienste

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.

4.  Geben Sie auf der Seite **Webdienst** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.

5.  Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Löschen von Konfigurationseinstellungen für Webdienste mithilfe von Windows PowerShell-Cmdlets

Sie können Webdienst-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsWebServiceConfiguration** löschen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>So löschen Sie bestimmte Konfigurationseinstellungen für Webdienste

  - Mit dem folgenden Befehl werden die Webdienstsicherheitseinstellungen für den Standort "Redmond" entfernt:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>So löschen Sie alle auf den Website Bereich angewendeten Konfigurationseinstellungen für den Webdienst

  - Mit dem folgenden Befehl werden alle auf Dienstebene angewendeten Webdienstsicherheitseinstellungen entfernt:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>So löschen Sie alle Webdienst-Konfigurationseinstellungen, die die Zertifikatauthentifizierung ermöglichen

  - Mit dem folgenden Befehl werden alle Webdienstsicherheitseinstellungen entfernt, die die Verwendung der Zertifikatauthentifizierung erlauben:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren der Authentifizierung in der lync Server 2013-Systemsteuerung](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

