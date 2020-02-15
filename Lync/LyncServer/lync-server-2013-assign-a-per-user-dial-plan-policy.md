---
title: 'Lync Server 2013: Zuweisen einer Richtlinie für den Wählplan auf Benutzerbasis'
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
ms.openlocfilehash: 9ea17e772bd98501b0d50674a2b82a9abb0e0b38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043707"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Zuweisen einer benutzerbezogenen Wähl Plan Richtlinie in lync Server 2013

 


Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden. Für die Benutzerkonten werden automatisch die globalen Wähleinstellungen verwendet oder, sofern vorhanden und Sie keine benutzerbezogenen Wähleinstellungen explizit zuweisen, die Wähleinstellungen auf Standortebene verwendet. Wenn Sie die globalen Wähleinstellungen oder den Standortwählplan für alle Benutzer verwenden möchten, die für Enterprise VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>So weisen Sie einen Wählplan mithilfe der lync Server 2013-Systemsteuerung zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, dem Sie Einwähleinstellungen zuweisen möchten.

6.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

7.  Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.

8.  Klicken Sie auf **Wählplanrichtlinie**, und wählen Sie dann die gewünschten Einwähleinstellungen aus.

9.  Klicken Sie auf **Commit**.

Ausführliche Informationen zum Konfigurieren von Wählplänen finden Sie unter [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) Thema.

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Zuweisen eines benutzerbezogenen Wählplans mithilfe von Windows PowerShell-Cmdlets

Sie können benutzerspezifische Wählpläne mit Windows PowerShell und dem Cmdlet **Grant-CsdialPlan** zuweisen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer einen Wählplan pro Benutzer zu

  - Mithilfe des folgenden Befehls werden dem Benutzer Ken Myer die benutzerbezogenen Einwähleinstellungen RedmondDialPlan zugewiesen.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>So weisen Sie mehreren Benutzern einen Wählplan pro Benutzer zu

  - Mithilfe dieses Befehls werden die benutzerbezogenen Einwähleinstellungen RedmondDialPlan allen Benutzern zugewiesen, die in Redmond arbeiten. Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>So heben Sie die Zuweisung von benutzerbezogenen Wähleinstellungen auf

  - Mithilfe des folgenden Befehls wird die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben, die Ken Myer zuvor zugewiesen wurde. Nachdem die Zuweisung der benutzerbezogenen Einwähleinstellungen aufgehoben wurde, wird Ken Myer automatisch mithilfe der globalen Einwähleinstellungen, seines lokalen Standortwählplans (sofern vorhanden) oder mithilfe der Wähleinstellungen auf Dienstebene für seine Registrierung oder sein PSTN-Gateway verwaltet. Wähleinstellungen auf Dienstebene haben Vorrang vor jeglichen Standortwählplänen, und ein Standortwählplan hat Vorrang vor den globalen Einwähleinstellungen.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema zum [Grant-CsDialPlan-](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) Cmdlet.

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Für lync Server 2013 aktivierte Benutzerkonten](lync-server-2013-user-accounts-enabled-for-lync-server.md)

