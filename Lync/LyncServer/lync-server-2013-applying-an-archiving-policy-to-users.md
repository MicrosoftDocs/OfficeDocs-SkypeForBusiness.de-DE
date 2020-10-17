---
title: 'Lync Server 2013: Anwenden einer Archivierungsrichtlinie auf Benutzer'
description: 'Lync Server 2013: Anwenden einer Archivierungsrichtlinie auf Benutzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544971"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn ein Benutzer für lync Server 2013 aktiviert wurde und Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die in lync Server 2013 verwaltet werden, können Sie die Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung der Archivierung interner Kommunikation erstellen, können Sie Sie auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der lync Server 2013 Kommunikation des Benutzers zu unterstützen.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration options in lync Server 2013 für Ihre Organisation, Standorte und Pools</A> in der Betriebsdokumentation.



</div>

Gehen Sie nach der in diesem Thema aufgeführten Anleitung vor, um eine zuvor erstellte Benutzerrichtlinie für Archivierung auf eine oder mehrere Benutzerkonten oder -gruppen anzuwenden.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>So wenden Sie eine Benutzerrichtlinie für die Archivierung auf ein Benutzerkonto an

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie dann nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie im Abschnitt **lync Server Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für die Server Installation übernommen. Diese Einstellungen werden automatisch vom Server angewendet.

    
    </div>

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Per-User Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Benutzerspezifische Archivierungsrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsArchivingPolicy** zugewiesen werden. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine benutzerspezifische Archivierungsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer "Ken Myer" zugewiesen.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine benutzerspezifische Archivierungsrichtlinie zu

  - Der folgende Befehl weist die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zu, deren Konten sich auf dem Registrierungsstellenpool "atl-cs-001.litwareinc.com" befinden. Ausführliche Informationen zu dem in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum [Get-CsUser-](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) Cmdlet.
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>So weisen Sie eine Archivierungsrichtlinie auf Benutzerebene zu

  - Der folgende Befehl hebt alle bestehenden Zuweisungen von benutzerbezogenen Archivierungsrichtlinien zu "Ken Myer" auf. Danach wird Ken Myer automatisch von der globalen Richtlinie oder, wenn vorhanden, von der Richtlinie für seinen lokalen Standort verwaltet. (Standortrichtlinien haben Vorrang vor der globalen Richtlinie).
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Ausführliche Informationen finden Sie in der Dokumentation zum [Grant-CsArchivingPolicy-](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Zuweisen von Richtlinien pro Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

