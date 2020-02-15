---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8464e64c3de1e85f823bb3e1b5dac4dd1837effd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer neuen clientversionsrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Mithilfe von clientversionsrichtlinien können Sie die Versionen von Clients angeben, die in Ihrer Umgebung unterstützt werden. Die Verwendung der Client Versionsverwaltung kann dazu beitragen, die mit der Unterstützung mehrerer Clientversionen verbundenen Kosten zu reduzieren. Es kann auch die gesamtbenutzerfreundlichkeit verbessern, da die verfügbaren Features bei einer Interaktion mit früheren und höheren Versionen der Clients durch die frühere Version des Clients limitiert werden können. Sie können clientversionsrichtlinien in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell erstellen oder ändern.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>So erstellen oder ändern Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**.
    
    <div>
    

    > [!NOTE]  
    > Die Registerkarte <STRONG>Clientversionsrichtlinie</STRONG> ist standardmäßig ausgewählt.

    
    </div>

4.  Führen Sie auf der Seite **Client Versionsrichtlinie** eine der folgenden Aktionen aus:
    
      - Um eine clientversionsrichtlinie zu erstellen, klicken Sie auf **neu**, wählen Sie **Standortrichtlinie**, **Pool Richtlinie**oder **Benutzerrichtlinie**aus, und klicken Sie dann auf **OK**.
    
      - Um die globale Richtlinie oder eine andere vorhandene clientversionsrichtlinie zu ändern, wählen Sie die Richtlinie aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  Erstellen oder ändern Sie auf der Seite **clientversionsrichtlinie bearbeiten** in lync Server 2013 die in [erstellen oder Ändern einer neuen clientversionsrichtlinien Regel](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)beschriebenen Regeln.

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Erstellen oder Ändern von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können clientversionsrichtlinien erstellen, indem Sie das Cmdlet **New-CsClientVersionPolicy** verwenden, und Sie mithilfe des Cmdlets "Cmdlet" **festlegen-CsClientVersionPolicy** ändern. Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>So erstellen Sie eine neue clientversionsrichtlinie für Standort Bereiche

  - Mit dem folgenden Befehl wird eine neue clientversionsrichtlinie erstellt, die auf den Standort "Redmond" angewendet wird. Da keine zusätzlichen Parameter angegeben werden, verwendet die neue Richtlinie die Standardeinstellungen für Clientversionen.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>So erstellen Sie eine neue clientversionsrichtlinie pro Benutzer

  - Verwenden Sie einen Befehl wie den folgenden, um eine benutzerspezifische Richtlinie zu erstellen:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Ausführliche Informationen finden Sie in den Hilfethemen für das [New-CsClientVersionPolicy-](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet und das Cmdlet "Set [-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) ".

</div>

</div>

<span> </span>

</div>

</div>

</div>

