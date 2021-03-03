---
title: Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. '
ms.openlocfilehash: f8e7e3576640e4c560cd620349f5c3afdaf541cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816325"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von SIP-Trunk-Konfigurationseinstellungen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch den Skype for Business ServerControl Panel oder das [Cmdlet "Remove-CsTrunkConfiguration"](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) verwenden, um die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Eigenschaft "Enable3pccRefer" auf "True" festgelegt haben, wird beim Zurücksetzen der globalen Auflistung die Eigenschaft "Enable3pccRefer" auf den Standardwert "False" zurückgesetzt.

Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen auf Standort- oder Dienstebene (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:

- Wenn Sie Einstellungen auf Dienstebene entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
- Wenn Sie Einstellungen auf Standortebene entfernen, werden alle mit diesen Einstellungen verwaltete SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

**So entfernen Sie Trunkkonfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung** 

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **"Sprachrouting"** und dann auf **"Trunkkonfiguration".**
2. Wählen Sie **auf der Registerkarte "Trunkkonfiguration"** die Auflistung der zu löschende Sip-Trunk-Konfigurationseinstellungen aus, klicken Sie auf "Bearbeiten" **und** dann auf **"Löschen".** Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt, und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
3. Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
5. Klicken Sie **im Dialogfeld "Skype for Business Server-Systemsteuerung"** auf **"OK".**
6. Wenn Sie Ihre Meinung ändern und sich entschließen, die Auflistung nicht zu löschen, klicken Sie auf **Commit,** und klicken Sie dann auf "Alle nicht ausgelassenen Änderungen **abbrechen".** Klicken Sie auf OK, wenn das Dialogfeld **"Skype for Business Server-Systemsteuerung"** **angezeigt wird.**

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Trunkkonfigurationseinstellungen mithilfe Windows PowerShell Cmdlets


Sie können Trunkkonfigurationseinstellungen mithilfe Windows PowerShell **remove-CsTrunkConfiguration-Cmdlets** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 

**So entfernen Sie eine angegebene Auflistung von Einstellungen**

Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort "Redmond" angewendet wurden:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**So entfernen Sie alle Auflistungen, die auf Websitebereich angewendet wurden**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf Dienstebene angewendet wurden:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**So entfernen Sie alle Auflistungen, in denen die Medienumgehung aktiviert ist**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsTrunkConfiguration".](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration)
