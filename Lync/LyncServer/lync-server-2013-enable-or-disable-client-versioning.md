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
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Aktivieren oder Deaktivieren der Client Versionsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle entweder global oder für bestimmte Websites zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit lync Server 2013 installiert und verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren. Wenn die globale Konfiguration aktiviert ist, werden alle von Ihnen eingerichteten clientversionsrichtlinien wirksam, wenn Benutzer versuchen, sich anzumelden. Sie können die Konfiguration der globalen Client Version deaktivieren, wenn keine Client Versionskontrolle erfolgen soll. Sie können die Client Versionsverwaltung über die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell aktivieren oder deaktivieren.

<div>


> [!NOTE]  
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>So aktivieren oder deaktivieren Sie die Client Versionsverwaltung mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Gehen Sie wie folgt vor:
    
      - Um die Client Versionsverwaltung Global zu aktivieren oder zu deaktivieren, doppelklicken Sie auf die **globale** Konfiguration, und ändern Sie dann die Einstellungen.
    
      - Um die Client Versionsverwaltung für eine bestimmte Website zu aktivieren oder zu deaktivieren, klicken Sie auf **neu**, wählen Sie die Website aus, klicken Sie auf **OK**, und ändern Sie dann die Einstellungen für die Website.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Client Versionsverwaltung mithilfe von Windows PowerShell-Cmdlets

Sie können die Client Versionsverwaltung mithilfe des Cmdlets " **festlegen-CsClientVersionConfiguration** " aktivieren oder deaktivieren. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-client-versioning"></a>So aktivieren Sie die Client Versionsverwaltung

  - Sie können die Client Versionsverwaltung aktivieren, indem Sie die **Enabled** -Eigenschaft auf true ($true) festlegen.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>So deaktivieren Sie die Client Versionsverwaltung

  - Sie können die Client Versionsverwaltung deaktivieren, indem Sie die **Enabled** -Eigenschaft auf false festlegen ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

