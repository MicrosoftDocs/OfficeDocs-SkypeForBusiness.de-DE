---
title: Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Clientversionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84df13c7abbc98cbb90c5b59a6b0717deb855e28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Sammlung von Konfigurationseinstellungen für Clientversionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Client Version-Konfigurationseinstellungen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit lync Server installiert und verwendet, um die Client Versionskontrolle für die gesamte Server Bereitstellung zu aktivieren oder zu deaktivieren. Sie können auch Konfigurationseinstellungen für Clientversionen für einzelne Websites konfigurieren. Sie können die Konfigurationseinstellungen für Clientversionen in der lync Server 2013-Systemsteuerung oder in der lync Server 2013-Verwaltungsshell erstellen oder ändern.

<div>


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen oder ändern Sie die Konfigurationseinstellungen für Clientversionen mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Führen Sie auf der Seite **Client Versions Konfiguration** die folgenden Aktionen aus:
    
      - Wenn Sie eine neue Konfiguration erstellen möchten, klicken Sie auf **neu**, wählen Sie eine Website aus, klicken Sie auf **OK** Name, und aktualisieren Sie die Einstellungen.
    
      - Wenn Sie eine Konfiguration ändern möchten, wählen Sie die Konfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und nehmen Sie die gewünschten Änderungen an den Einstellungen vor.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen oder Ändern von Client Versions Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen für Clientversionen mithilfe des Cmdlets **New-CsClientVersionConfiguration** erstellen und mithilfe des Cmdlets " **Satz-CsClientVersionConfiguration** " ändern. Diese Cmdlets können entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>So erstellen Sie eine neue Sammlung von Konfigurationseinstellungen für Clientversionen

  - Mit dem folgenden Befehl wird eine neue Sammlung von Client Versions-Konfigurationseinstellungen erstellt, die auf die Redmond-Website angewendet wurden. In diesem Beispiel ist die Client Versionsverwaltung für die Redmond-Website deaktiviert.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>So aktivieren Sie die Client Versionsverwaltung für eine Website

  - Mit diesem Befehl wird die Client Versionsverwaltung für die Redmond-Website aktiviert.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>So deaktivieren Sie die Client Versionsverwaltung in der gesamten Organisation

  - In diesem Beispiel ist die Client Versionsverwaltung für alle Konfigurationseinstellungen der Client Version deaktiviert, die in der Organisation verwendet werden.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) und [CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

