---
title: Skype for Business Server – Löschen einer vorhandenen Auflistung von SIP-Trunkkonfigurationseinstellungen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. '
ms.openlocfilehash: 09e51dd54401b761c448872545111e8bebf01599
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760613"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server – Löschen einer vorhandenen Auflistung von SIP-Trunkkonfigurationseinstellungen

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Skype for Business Server installieren, wird eine globale Auflistung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch den Skype for Business ServerControl-Bereich oder das Cmdlet ["Remove-CsTrunkConfiguration"](/powershell/module/skype/Remove-CsTrunkConfiguration) verwenden, um die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Enable3pccRefer-Eigenschaft auf "True" festgelegt haben, wird beim Zurücksetzen der globalen Auflistung die Enable3pccRefer-Eigenschaft auf den Standardwert "False" zurückgesetzt.

Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen auf Standort- oder Dienstebene (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:

- Wenn Sie Einstellungen auf Dienstebene entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.
- Wenn Sie Einstellungen auf Standortebene entfernen, werden alle mit diesen Einstellungen verwaltete SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

**So entfernen Sie Trunkkonfigurationseinstellungen mit der Skype for Business Server Systemsteuerung** 

1. Klicken Sie in der systemsteuerung Skype for Business Server auf **VoIP-Routing** und dann auf **Trunkkonfiguration.**
2. Wählen Sie auf der Registerkarte **"Trunkkonfiguration"** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **"Bearbeiten"** und dann auf **"Löschen".** Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt, und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.
3. Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.
4. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
5. Klicken Sie im Dialogfeld **Skype for Business Server Systemsteuerung** auf **OK.**
6. Wenn Sie Ihre Meinung ändern und sich entscheiden, die Auflistung nicht zu löschen, klicken Sie auf **"Commit"** und dann auf **"Alle nicht übernommenen Änderungen abbrechen".** Wenn das Dialogfeld **Skype for Business Server Systemsteuerung** angezeigt wird, klicken Sie auf **OK.**

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Trunkkonfigurationseinstellungen mithilfe Windows PowerShell Cmdlets


Sie können Trunkkonfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **"Remove-CsTrunkConfiguration"** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

**So entfernen Sie eine angegebene Auflistung von Einstellungen**

Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort "Redmond" angewendet wurden:

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**So entfernen Sie alle Auflistungen, die auf den Websitebereich angewendet wurden**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf Dienstebene angewendet wurden:

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**So entfernen Sie alle Auflistungen, in denen die Medienumgehung aktiviert ist**

Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsTrunkConfiguration".](/powershell/module/skype/Remove-CsTrunkConfiguration)
