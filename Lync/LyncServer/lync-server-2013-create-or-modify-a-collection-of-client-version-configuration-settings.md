---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen
description: Erstellen oder ändern Sie eine Sammlung von Konfigurationseinstellungen für Clientversionen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0082b618b8417c9d0da44599f1606cd238dfd7e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578311"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Clientversionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle zu aktivieren oder zu deaktivieren. Die Konfiguration der globalen Client Version wird mit lync Server installiert und dient zum Aktivieren oder Deaktivieren der Client Versionskontrolle für die gesamte Server Bereitstellung. Sie können auch Konfigurationseinstellungen für Clientversionen für einzelne Websites konfigurieren. Sie können Client Versions Konfigurationseinstellungen in lync Server 2013 Systemsteuerung oder in lync Server 2013 Verwaltungsshell erstellen oder ändern.

<div>


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen oder ändern Sie Konfigurationseinstellungen für Clientversionen mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Führen Sie auf der Seite **Client Versions Konfiguration** die folgenden Aktionen aus:
    
      - Um eine neue Konfiguration zu erstellen, klicken Sie auf **neu**, wählen Sie einen Standort aus, klicken Sie auf **OK** Name, und aktualisieren Sie die Einstellungen.
    
      - Um eine Konfiguration zu ändern, wählen Sie die Konfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und nehmen Sie Änderungen an den Einstellungen vor.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen oder Ändern von Konfigurationseinstellungen für Client Versionen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen für Clientversionen mithilfe des **New-CsClientVersionConfiguration-** Cmdlets erstellen und diese mithilfe des Cmdlets " **CsClientVersionConfiguration** " ändern. Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>So erstellen Sie eine neue Auflistung von Konfigurationseinstellungen für Clientversionen

  - Mit dem folgenden Befehl wird eine neue Auflistung von Client Versions-Konfigurationseinstellungen erstellt, die auf den Standort "Redmond" angewendet werden. In diesem Beispiel ist die Client Versionsverwaltung für den Standort "Redmond" deaktiviert.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>So aktivieren Sie die Client Versionsverwaltung für einen Standort

  - Mit diesem Befehl wird die Client Versionsverwaltung für den Standort "Redmond" aktiviert.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>So deaktivieren Sie die Client Versionsverwaltung in der gesamten Organisation

  - In diesem Beispiel ist die Client Versionsverwaltung für alle Client Versions Konfigurationseinstellungen deaktiviert, die in der Organisation verwendet werden.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) und [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

