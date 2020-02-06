---
title: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie in der Skype for Business Server-Systemsteuerung SIP Federation, Remote User Access und Public Instant Messaging (im) konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden.
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818326"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer zu einem Skype for Business-aktivierten Benutzer

Wenn ein Benutzer für Skype for Business Server aktiviert wurde, können Sie in der Skype for Business Server-Systemsteuerung SIP Federation, Remote User Access und Public Instant Messaging (im) konfigurieren, indem Sie die entsprechenden Richtlinien auf bestimmte Benutzer anwenden. Wenn Sie beispielsweise eine Richtlinie zur Unterstützung des Remotebenutzerzugriffs erstellt haben, müssen Sie Sie auf den Benutzer anwenden, bevor der Benutzer von einem Remotestandort aus eine Verbindung mit Skype for Business Server herstellen und mit internen Benutzern am Remotestandort zusammenarbeiten kann.


> [!NOTE]  
> Wenn Sie den Zugriff durch externe Benutzer unterstützen möchten, müssen Sie die Unterstützung für jeden Typ von externem Benutzer Zugriff aktivieren, den Sie unterstützen möchten, und die entsprechenden Richtlinien und anderen Optionen zum Steuern der Verwendung konfigurieren. Ausführliche Informationen finden Sie unter [Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).


Verwenden Sie das in diesem Thema beschriebene Verfahren, um eine zuvor erstellte Richtlinie für den Benutzer Zugriff auf ein oder mehrere Benutzerkonten anzuwenden.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>So wenden Sie eine externe Benutzerrichtlinie auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff**die Benutzerrichtlinie aus, die Sie anwenden möchten.
     
> [!NOTE]  
> Die Einstellungen für ** \<automatische>** wenden die Standardeinstellungen für Server oder globale Richtlinie an.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Zuweisen von externen Zugriffsrichtlinien für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Cmdlet Grant-CsExternalAccessPolicy zugewiesen werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>So weisen Sie einem einzelnen Benutzer eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Mit diesem Befehl wird dem Benutzer Ken Myers die Richtlinie für den externen Zugriff per Benutzer RedmondExternalAccessPolicy zugewiesen.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>So weisen Sie mehreren Benutzern eine Richtlinie für den externen Zugriff pro Benutzer zu

  - Dieser Befehl weist allen Benutzern, die über Konten in der United States ou in Active Directory verfügen, die USAExternalAccessPolicy-Richtlinie für den externen Zugriff pro Benutzer zu. Weitere Informationen zu dem in diesem Befehl verwendeten ou-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>So heben Sie die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer auf

  - Mit diesem Befehl wird die Zuweisung einer externen Zugriffsrichtlinie für einzelne Benutzer aufheben, die Ken Myers zuvor zugewiesen wurde. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


