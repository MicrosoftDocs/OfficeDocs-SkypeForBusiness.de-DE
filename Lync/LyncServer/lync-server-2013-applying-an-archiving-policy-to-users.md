---
title: 'Lync Server 2013: Anwenden einer Archivierungsrichtlinie auf Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56bb6705187172888c9fdac33532e25a210e8246
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Anwenden einer Archivierungsrichtlinie auf Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn ein Benutzer für lync Server 2013 aktiviert wurde und Sie eine oder mehrere Benutzerrichtlinien für die Archivierung für Benutzer erstellt haben, die sich auf lync Server 2013 befinden, können Sie die Archivierungsunterstützung für bestimmte Benutzer implementieren, indem Sie die entsprechenden Richtlinien auf diese Benutzer oder Benutzergruppen anwenden. Wenn Sie beispielsweise eine Richtlinie erstellen, um die Archivierung interner Kommunikation zu unterstützen, können Sie diese auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung der lync Server 2013-Kommunikation des Benutzers zu unterstützen.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Websites und Pools</A> in der Betriebsdokumentation.



</div>

Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Archivierungs Benutzerrichtlinie auf ein oder mehrere Benutzerkonten oder Benutzergruppen anzuwenden.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>So wenden Sie eine Archivierungs Benutzerrichtlinie auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie**die Archivierungs Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen gelten für die standardmäßigen Server Installationseinstellungen. Diese Einstellungen werden vom Server automatisch übernommen.

    
    </div>

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Zuweisen einer pro-Benutzer-Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Archivierungsrichtlinien für einzelne Benutzer können mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsArchivingPolicy** zugewiesen werden. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Archivierungsrichtlinie pro Benutzer zu

  - Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie „RedmondArchivingPolicy“ dem Benutzer Jonas Baar zugeordnet.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer mehreren Benutzern zu

  - Dieser Befehl weist allen Benutzern, die Konten im Registrierungspool ATL-CS-001.litwareinc.com haben, die Archivierungsrichtlinien für einzelne Benutzer zu RedmondArchivingPolicy. Details zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation zum Cmdlet " [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) ".
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>So weisen Sie eine Archivierungsrichtlinie für einzelne Benutzer zu

  - Mit dem folgenden Befehl wird die Zuweisung einer pro-Benutzer-Archivierungsrichtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Ausführliche Informationen finden Sie in der Dokumentation zu [Grant-CsArchivingPolicy-](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) Cmdlets.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

