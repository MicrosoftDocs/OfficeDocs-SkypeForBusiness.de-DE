---
title: Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274933"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server

SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:

- Ob Medienumgehung für die Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.
- Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch das Skype for Business servercontrol-Panel oder das Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) verwenden, um die Eigenschaften in der globalen Sammlung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Eigenschaft „Enable3pccRefer“ auf „True“ setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert „False“ zurückgesetzt.

Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen für den Standort- oder Dienstbereich (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:

- Wenn Sie Einstellungen für den Dienstbereich entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
- Wenn Sie Einstellungen für den Standortbereich entfernen, werden alle mit diesen Einstellungen verwalteten SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

**So entfernen Sie die trunk-Konfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung** 

1. Klicken Sie im Skype for Business Server-Control Panel auf **VoIP-Routing**und dann auf trunk- **Konfiguration**.
2. Wählen Sie auf der Registerkarte **trunk Configuration** die Sammlung der zu löschenden SIP-Trunk-Konfigurationseinstellungen aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
3. Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
5. Klicken Sie im Dialogfeld **Skype for Business Server Control Panel** auf **OK**.
6. Wenn Sie es sich anders überlegen und die Sammlung nicht löschen möchten, klicken Sie auf **Commit**, und klicken Sie dann auf **alle nicht übernommenen Änderungen abbrechen**. Wenn das Dialogfeld " **Skype for Business Server Control Panel** " angezeigt wird, klicken Sie auf **OK**.

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von trunk-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets


Sie können trunk-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsTrunkConfiguration** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

**So entfernen Sie eine angegebene Auflistung von Einstellungen**

Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort „Redmond“ angewendet wurden:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**So entfernen Sie alle Auflistungen, die im Standortbereich angewendet wurden**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf den Dienstbereich angewendet wurden:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**So entfernen Sie alle Auflistungen, bei denen die Medienumgehung aktiviert ist**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) .
