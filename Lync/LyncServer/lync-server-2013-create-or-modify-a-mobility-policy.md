---
title: 'Lync Server 2013: Erstellen oder Ändern einer Mobilitätsrichtlinie'
description: 'Lync Server 2013: Erstellen oder Ändern einer Mobilitätsrichtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcf593c568a8ecf1bd6791641affc4076672b250
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566101"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer Mobilitätsrichtlinie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können mobilitätsrichtlinien erstellen oder ändern, um mobilen Benutzern die Verwendung unterstützter mobiler Geräte für lync-Funktionen wie Instant Messaging (Sofortnachrichten), Anwesenheit und Kontakte zu ermöglichen. Sie können mobilitätsrichtlinien in lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell erstellen oder ändern.

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>So erstellen Sie eine Mobilitätsrichtlinie mit lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf **neu**, und führen Sie einen der folgenden Schritte aus:
    
    1.  Klicken Sie zum Erstellen einer Website Mobilitätsrichtlinie auf **Website Richtlinie**, klicken Sie auf einen Standort, klicken Sie auf **OK**, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.
    
    2.  Um eine Benutzer Mobilitätsrichtlinie zu erstellen, klicken Sie auf **Benutzerrichtlinie**, geben Sie einen Namen ein, überprüfen Sie die Standardeinstellungen, und nehmen Sie bei Bedarf Änderungen vor.

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>So ändern Sie eine Mobilitätsrichtlinie mit lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Mobilitätsrichtlinie** .

4.  Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf eine der vorhandenen mobilitätsrichtlinien.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

6.  Bearbeiten Sie eine der Einstellungen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Erstellen von Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Sie können mobilitätsrichtlinien (auf Standortebene oder auf Benutzerebene) erstellen, indem Sie Windows PowerShell und das Cmdlet **New-CsMobilityPolicy** verwenden. Darüber hinaus können Sie mit dem Cmdlet " **CsMobilityPolicy** " alle vorhandenen Richtlinien ändern, einschließlich der globalen Richtlinie. Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>So erstellen Sie eine Mobilitätsrichtlinie auf Standortebene

  - Mit diesem Befehl wird eine neue Mobilitätsrichtlinie für den Standort "Redmond" erstellt:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden die Standardwerte für alle Eigenschaften der Richtlinie verwendet.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>So erstellen Sie eine Mobilitätsrichtlinie auf Benutzerebene

  - Um eine Mobilitätsrichtlinie auf Benutzerebene zu erstellen, geben Sie eine eindeutige Identität für die Richtlinie an:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen einer Mobilitätsrichtlinie

  - Um Richtlinien mit unterschiedlichen Eigenschaftswerten zu erstellen, schließen Sie den entsprechenden Parameter und Parameterwert ein. Mit diesem Befehl wird beispielsweise eine Mobilitätsrichtlinie erstellt, mit der die Funktion "Anruf über Arbeit" deaktiviert wird:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>So ändern Sie beim Erstellen einer Mobilitätsrichtlinie mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Mit diesem Befehl wird beispielsweise eine Richtlinie erstellt, die sowohl die Mobilität als auch die Funktion "Anruf über" deaktiviert:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Ausführliche Informationen finden Sie im Hilfethema zu den Cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) und [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von mobilitätsrichtlinien in lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

