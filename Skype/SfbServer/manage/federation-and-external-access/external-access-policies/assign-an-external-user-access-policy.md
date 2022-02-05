---
title: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer
ms.reviewer: null
'ms:assetid': 736fcaad-9f95-4896-b767-e199d86a00a4
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)'
'ms:contentKeyID': 48184483
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie SIP-Partnerverbund, Remotebenutzerzugriff und Verbindungen mit öffentlichen Chatnachrichten in der Skype for Business Server Systemsteuerung konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden.'
---


# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem Skype for Business aktivierten Benutzer

Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie SIP-Partnerverbund, Remotebenutzerzugriff und Verbindungen mit öffentlichen Chatnachrichten in der Skype for Business Server Systemsteuerung konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit Skype for Business Server herstellen und mit internen Benutzern vom Remotestandort aus zusammenarbeiten kann.


> [!NOTE]  
> Um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie die Unterstützung für jeden Typ des externen Benutzerzugriffs aktivieren, der unterstützt werden soll, sowie die entsprechenden Richtlinien und andere Optionen zur Verwendungssteuerung konfigurieren. Ausführliche Informationen finden Sie unter [Verwalten des Partnerverbunds und des externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).


Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte Richtlinie für den externen Benutzerzugriff auf ein oder mehrere Benutzerkonten anzuwenden.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>So wenden Sie eine Richtlinie für den externen Benutzerzugriff auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie unter **"Skype for Business Server Benutzer** bearbeiten" unter **"Richtlinie für den externen Zugriff**" die Benutzerrichtlinie aus, die Sie anwenden möchten.
     
> [!NOTE]  
> Die **\<Automatic>** Einstellungen gelten für den Standardserver oder die globalen Richtlinieneinstellungen.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Zuweisen Per-User Richtlinien für den externen Zugriff mithilfe Windows PowerShell Cmdlets

Richtlinien für den externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Cmdlet Grant-CsExternalAccessPolicy zugewiesen werden. Dieses Cmdlet kann entweder über die Skype for Business Server Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Benutzerrichtlinie für den externen Zugriff zu

  - Mit diesem Befehl wird dem Benutzer Ken Myer die Richtlinie „RedmondExternalAccessPolicy“ für den externen Zugriff auf Benutzerebene zugewiesen.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Benutzerbasierte Richtlinie für den externen Zugriff zu

  - Mit diesem Befehl wird die Richtlinie „USAExternalAccessPolicy“ für den externen Zugriff auf Benutzerebene allen Benutzern zugewiesen, die Active Directory ein Konto in der Organisationseinheit „UnitedStates“ besitzen. Weitere Informationen zum ou-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum [Cmdlet "Get-CsUser](/powershell/module/skype/Get-CsUser) ".<br/><br/>Get-CsUser -OU "ou=United States,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>So heben Sie die Zuweisung einer Benutzerrichtlinie für den externen Zugriff auf

  - Mit diesem Befehl wird die Zuweisung sämtlicher Richtlinien für den externen Zugriff auf Benutzerebene, die dem Benutzer Ken Myer zuvor zugeordnet wurden, aufgehoben. Nach der Aufhebung der Richtlinie auf Benutzerebene wird Ken Myer automatisch unter Verwendung der globalen Richtlinie bzw. (sofern vorhanden) von der Richtlinie seines lokalen Standorts verwaltet. Die Standortrichtlinie hat Vorrang vor der globalen Richtlinie.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null


Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) ".
