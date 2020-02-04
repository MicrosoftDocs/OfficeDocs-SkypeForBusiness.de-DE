---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523907fbf4bc4cca93be8e529b6b607b43f0ea87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Wenn ein Benutzer für lync Server aktiviert wurde, können Sie den SIP-Verbund, die XMPP-Föderation, den Remotebenutzerzugriff und die öffentliche Sofortnachrichten-Konnektivität in der lync Server-Systemsteuerung konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie Sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit lync Server herstellen und mit internen Benutzern am Remotestandort zusammenarbeiten kann.

<div>


> [!NOTE]  
> Wenn Sie den Zugriff durch externe Benutzer unterstützen möchten, müssen Sie die Unterstützung für jeden Typ von externem Benutzer Zugriff aktivieren, den Sie unterstützen möchten, und die entsprechenden Richtlinien und anderen Optionen zum Steuern der Verwendung konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013</A> in der Betriebsdokumentation.



</div>

Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Richtlinie für den Benutzer Zugriff auf ein oder mehrere Benutzerkonten anzuwenden.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>So wenden Sie eine externe Benutzerrichtlinie auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **lync Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff**die Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen gelten für den Standardserver oder die globalen Richtlinieneinstellungen.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Zuweisen von externen Zugriffsrichtlinien für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Cmdlet Grant-CsExternalAccessPolicy zugewiesen werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Mit diesem Befehl wird dem Benutzer Ken Myers die Richtlinie für den externen Zugriff per Benutzer RedmondExternalAccessPolicy zugewiesen.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Dieser Befehl weist allen Benutzern, die über Konten in der United States ou in Active Directory verfügen, die USAExternalAccessPolicy-Richtlinie für den externen Zugriff pro Benutzer zu. Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>So heben Sie die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer auf

  - Mit diesem Befehl wird die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer aufheben, die Ken Myers zuvor zugewiesen wurde. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

