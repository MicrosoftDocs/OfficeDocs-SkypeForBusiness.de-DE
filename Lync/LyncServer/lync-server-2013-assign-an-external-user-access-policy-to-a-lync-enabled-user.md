---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem lync-aktivierten Benutzer'
description: 'Lync Server 2013: Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer.'
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
ms.openlocfilehash: 2be3ea52e6e44400b3967d7c3346da2297220675
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573461"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Zuweisen einer Richtlinie für den externen Benutzer Zugriff zu einem lync-aktivierten Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Wenn ein Benutzer für lync Server aktiviert wurde, können Sie den SIP-Partnerverbund, den XMPP-Verbund, den Remotebenutzerzugriff und die Verbindung mit öffentlichen Instant Messaging-Verbindungen im lync Server-Systemsteuerung konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie Sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit lync Server herstellen und mit internen Benutzern am Remotestandort zusammenarbeiten kann.

<div>


> [!NOTE]  
> Um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie die Unterstützung für jeden Typ des externen Benutzerzugriffs aktivieren, der unterstützt werden soll, sowie die entsprechenden Richtlinien und andere Optionen zur Verwendungssteuerung konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</A> in der Bereitstellungsdokumentation oder im <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013</A> in der Betriebsdokumentation.



</div>

Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Richtlinie für den externen Benutzerzugriff auf ein oder mehrere Benutzerkonten anzuwenden.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>So wenden Sie eine Richtlinie für den externen Benutzerzugriff auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff** die Benutzerrichtlinie aus, die Sie anwenden möchten.
    
    <div>
    

    > [!NOTE]  
    > Durch die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen werden die Standardeinstellungen für Server oder globale Richtlinien übernommen.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Zuweisen von Per-User Richtlinien für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff auf Benutzerbasis können mithilfe von Windows PowerShell und dem Grant-CsExternalAccessPolicy-Cmdlet zugewiesen werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Mit diesem Befehl wird dem Benutzer Ken Myer die Richtlinie „RedmondExternalAccessPolicy“ für den externen Zugriff auf Benutzerebene zugewiesen.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Mit diesem Befehl wird die Richtlinie „USAExternalAccessPolicy“ für den externen Zugriff auf Benutzerebene allen Benutzern zugewiesen, die Active Directory ein Konto in der Organisationseinheit „UnitedStates“ besitzen. Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>So heben Sie die Zuweisung einer Richtlinie für den externen Zugriff auf einzelne Benutzer auf

  - Mit diesem Befehl wird die Zuweisung sämtlicher Richtlinien für den externen Zugriff auf Benutzerebene, die dem Benutzer Ken Myer zuvor zugeordnet wurden, aufgehoben. Nach der Aufhebung der Richtlinie auf Benutzerebene wird Ken Myer automatisch unter Verwendung der globalen Richtlinie bzw. (sofern vorhanden) von der Richtlinie seines lokalen Standorts verwaltet. Die Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsExternalAccessPolicy-](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

