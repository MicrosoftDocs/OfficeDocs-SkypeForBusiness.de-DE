---
title: 'Lync Server 2013: Zuweisen einer benutzerbezogenen Wähl Plan Richtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722965"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Zuweisen einer benutzerseitigen Wähl Plan Richtlinie in lync Server 2013

 


Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein. Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Websiteebene, wenn Sie nicht explizit einen vorhandenen Wählplan für einzelne Benutzer zuweisen. Wenn Sie den Global-oder Website-Wählplan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>So weisen Sie mithilfe der lync Server 2013-Systemsteuerung einen Wählplan zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, dem Sie einen Wählplan zuweisen möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.

8.  Klicken Sie auf **Wähl Plan Richtlinie**, und wählen Sie dann den gewünschten Wählplan aus.

9.  Klicken Sie auf **Commit ausführen**.

Details zum Konfigurieren von Wählplänen finden Sie im Thema [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Zuweisen eines pro-Benutzer-Wählplans mithilfe von Windows PowerShell-Cmdlets

Sie können Wählpläne für einzelne Benutzer mit Windows PowerShell und dem Cmdlet **Grant-CsdialPlan** zuweisen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu

  - Mit dem folgenden Befehl wird dem Benutzer Ken Myers der benutzerspezifische Wählplan redmonddialplan "zugewiesen.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu

  - Dieser Befehl weist allen Benutzern, die in Redmond arbeiten, den benutzerseitigen Wähl Plan redmonddialplan "zu. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf

  - Mit dem folgenden Befehl werden alle benutzerseitigen Wähleinstellungen, die Ken Myers zuvor zugewiesen wurden, aufheben. Nachdem der benutzerspezifische Wählplan nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe des globalen Wählplans, seines Orts Wähl Plans (sofern vorhanden) oder des Dienstbereichs-Wählplans verwaltet, der seiner Registrierungsstelle oder einem PSTN-Gateway zugewiesen ist. Ein Dienstbereichs-Wählplan hat Vorrang vor jedem Website Wählplan, und ein Website Wählplan hat Vorrang vor dem globalen Wählplan.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Für lync Server 2013 aktivierte Benutzerkonten](lync-server-2013-user-accounts-enabled-for-lync-server.md)

