---
title: Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie die SIP-Verbund, Remotebenutzerzugriff und öffentlichen Instant messaging-Diensten in der Skype Business Server-Systemsteuerung durch Anwenden geeigneten Richtlinien auf bestimmte Benutzer konfigurieren.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881500"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Zuweisen einer Richtlinie für den externen Benutzerzugriff zu einer Skype für Geschäftsbenutzer aktiviert

Wenn ein Benutzer für Skype für Business Server aktiviert wurde, können Sie die SIP-Verbund, Remotebenutzerzugriff und öffentlichen Instant messaging-Diensten in der Skype Business Server-Systemsteuerung durch Anwenden geeigneten Richtlinien auf bestimmte Benutzer konfigurieren. Beispielsweise wenn Sie eine Richtlinie zur Unterstützung des Zugriffs durch Remotebenutzer erstellt haben, müssen Sie sie anwenden, die dem Benutzer, bevor der Benutzer kann und Herstellen einer Verbindung mit Skype für Business Server von einem Remotestandort mit internen Benutzern von remote-Standort zusammenarbeiten.


> [!NOTE]  
> Zur Unterstützung der Zugriff durch externe Benutzer müssen Sie Aktivieren der Unterstützung für jede Art von Zugriff durch externe Benutzer, den Sie unterstützen möchten, und konfigurieren Sie geeigneten Richtlinien und andere Optionen, deren Verwendung steuern. Weitere Informationen hierzu finden Sie unter [Managing Federation und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md).


Verwenden Sie das Verfahren in diesem Thema, um eine zuvor erstellte externe Benutzerrichtlinie auf einen oder mehrere Benutzerkonten anzuwenden.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Anwenden eine Richtlinie für externe Benutzer auf ein Benutzerkonto

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Skype für Business Server-Benutzer bearbeiten** unter **Richtlinie für den externen Zugriff**die Benutzerrichtlinie aus, der Sie anwenden möchten.
     
> [!NOTE]  
> Die ** \<Automatic>** Einstellungen gelten die Standardeinstellungen des Servers oder globale Richtlinieneinstellungen.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Zuweisen von Richtlinien für externen Zugriff pro Benutzer mithilfe von Windows PowerShell-Cmdlets

Richtlinien für externen Zugriff pro Benutzer können mithilfe von Windows PowerShell und dem Grant-CsExternalAccessPolicy-Cmdlet zugewiesen werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>So weisen eine externe Zugriffsrichtlinie pro Benutzer zu einem einzelnen Benutzer

  - Mit diesem Befehl wird dem Benutzer Ken Myer die externen Zugriff benutzerbasierte Richtlinie "redmondexternalaccesspolicy" zugewiesen.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>So weisen eine externe Zugriffsrichtlinie pro Benutzer zu mehreren Benutzern

  - Dieser Befehl weist die benutzerbasierte Zugriff durch externe Richtlinie USAExternalAccessPolicy alle Benutzer mit Konten in den Vereinigten Staaten Organisationseinheit in Active Directory. Weitere Informationen zu der OU-Parameter, die in dieser Befehl verwendet finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Zum Aufheben der Zuweisung einer externen Zugriffsrichtlinie pro Benutzer

  - Mit diesem Befehl unassigns pro Benutzer externe Zugriffsrichtlinien zuvor Ken Myer zugewiesen. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Weitere Informationen finden Sie im Hilfethema zum [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) -Cmdlet.


