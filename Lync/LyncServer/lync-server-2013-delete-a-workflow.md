---
title: 'Lync Server 2013: Löschen eines Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Löschen eines Workflows in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren, um einen Workflow zu löschen.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>So verwenden Sie die lync Server-Systemsteuerung Löschen eines Workflows

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Workflow**.

4.  Klicken Sie auf der Seite **Workflow** auf **Workflow erstellen oder bearbeiten**.

5.  Geben Sie im Feld **Dienstsuche auswählen einen** Teil des Namens des **ApplicationServer** -Diensts ein, der den zu löschenden Workflow hostet.

6.  Klicken Sie in der Liste der Dienste auf den gewünschten Dienst, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Die Webseite des Reaktionsgruppen-Konfigurationstools wird geöffnet. Sie können die Webseite für das Reaktionsgruppen-Konfigurations Tool auch direkt in einem Webbrowser öffnen, indem Sie eine Verbindung mit <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>herstellen.

    
    </div>

7.  Suchen Sie unter **vorhandenen Workflow verwalten**nach dem Workflow, den Sie löschen möchten, und klicken Sie dann unter **Aktion**auf **Löschen**.

8.  Klicken Sie auf **Ja**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>So löschen Sie einen Workflow mithilfe von Windows PowerShell

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Beispiel:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

