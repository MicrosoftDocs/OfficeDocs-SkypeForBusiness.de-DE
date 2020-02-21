---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Client Versionsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c575a861644c27a0dba93790667ece9b973211e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Aktivieren oder Deaktivieren der Client Versionsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle entweder global oder für bestimmte Websites ein-oder auszuschalten. Die Konfiguration der globalen Client Version wird mit lync Server 2013 installiert und dient zum Aktivieren oder Deaktivieren der Client Versionskontrolle für die gesamte Server Bereitstellung. Wenn die globale Konfiguration aktiviert ist, werden alle clientversionsrichtlinien, die Sie in Kraft setzen, wirksam, wenn sich Benutzer anmelden. Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle ausgeführt werden soll. Sie können die Client Versionsverwaltung in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell aktivieren oder deaktivieren.

<div>


> [!NOTE]  
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>So aktivieren oder deaktivieren Sie die Client Versionsverwaltung mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Gehen Sie wie folgt vor:
    
      - Um die Client Versionsverwaltung Global zu aktivieren oder zu deaktivieren, doppelklicken Sie auf die **globale** Konfiguration, und ändern Sie dann die Einstellungen.
    
      - Klicken Sie auf **neu**, wählen Sie den Standort aus, klicken Sie auf **OK**, und ändern Sie dann die Einstellungen für die Website, um die Client Versionsverwaltung für eine bestimmte Website zu aktivieren oder zu deaktivieren.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Client Versionsverwaltung mithilfe von Windows PowerShell-Cmdlets

Sie können die Client Versionsverwaltung mithilfe des Cmdlets " **CsClientVersionConfiguration** " aktivieren oder deaktivieren. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-client-versioning"></a>So aktivieren Sie die Client Versionsverwaltung

  - Sie können die Client Versionsverwaltung aktivieren, indem Sie die **Enabled** -Eigenschaft auf true ($true) festlegen.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>So deaktivieren Sie die Client Versionsverwaltung

  - Sie können die Client Versionsverwaltung deaktivieren, indem Sie die **Enabled** -Eigenschaft auf false ($false) festlegen.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

