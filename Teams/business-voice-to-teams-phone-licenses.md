---
title: Wechseln von Business Voice zu Microsoft Teams Phone-Lizenzen
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Business Voice-Lizenzen in Microsoft Teams Phone-Lizenzen ändern.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6e7622e4b78e57f45209b90a525eb5fefbe8cd66
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271230"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Wechseln von Business Voice zu Microsoft Teams Phone-Lizenzen

Bis Ende Juni 2022 wird Business Voice eingestellt, daher [empfehlen wir Unternehmen, zu Microsoft Teams Telefon mit Anrufplan Bundlelizenzen zu wechseln](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice hat die folgenden drei Teams-Add-On-Lizenzen gebündelt:

- **Microsoft Teams Telefon** für ein cloudbasiertes Telefonsystem in Microsoft Teams.
- **Audiokonferenzen** für Ein- und Ausgehende Konferenzen für Besprechungen.
- **Microsoft Calling Plans** for domestic calls to Public Switched Telephone Network (PSTN) connectivity.

Vorhandene Business Voice-Kunden werden nicht automatisch auf das neue Lizenzierungsmodell umgestellt.

Dieser Artikel richtet sich an IT-Administratoren, die ihre Business Voice-Lizenzen in Microsoft Teams Telefon- und Audiokonferenzlizenzen ändern und dabei die gleichen Funktionen beibehalten müssen.

> [!WARNING]
> Folgen Sie den Anweisungen dieses Artikels genau. Wenn Sie in den Anweisungen aufgefordert werden, die Schaltfläche " **Speichern** " NICHT auszuwählen, wählen Sie nicht die Schaltfläche " **Speichern** " aus.
>
> Das vorzeitige Speichern kann dazu führen, dass Telefonnummernzuweisungen, Wählpläne, automatische Telefonzentralen und Anrufwarteschleifen verloren gehen.

## <a name="acquire-new-licenses"></a>Neue Lizenzen erwerben

Bevor Sie Business Voice-Lizenzen ersetzen, müssen Sie zuerst Ersatzlizenzen für Ihre Benutzer erwerben.

Sie benötigen Lizenzen, um diese Features bereitzustellen:

- Audiokonferenz
- Cloudbasiertes Telefonsystem
- PSTN-Konnektivität

Verwenden Sie die folgende Tabelle, um basierend auf Ihren Anforderungen zu ermitteln, welche Lizenzen erworben werden sollen:

| Alter Lizenzplan | Empfohlener Lizenzplan | Beschreibung |
| ---------------- | ------------------------ | ----------- |
| Business Voice mit Anrufplan | Teams-Telefon mit Anrufplan und Microsoft Teams Audiokonferenz mit Ausgehendwahl in die USA/CAN | Stellt cloudbasierte Telefonsystemfunktionen, einen Anrufplan für Inlandsanrufe mit Microsoft als PSTN-Anbieter sowie Ein- und Einwahlfunktionen für Besprechungsteilnehmer bereit, die von einem lizenzierten Benutzer organisiert werden. |
| Business Voice ohne Anrufplan | Teams Telefon Standard und Microsoft Teams Audiokonferenz mit Einwahl nach USA/CAN | Bietet cloudbasierte Telefonsystemfunktionen, die mit [einem Anrufplan eines Drittanbieters mit einem PSTN-Anbieter kombiniert werden können, indem Telefonieanbieter oder Direct Routing](pstn-connectivity.md) sowie Ein- und Einwahlfunktionen für Besprechungsteilnehmer verwendet werden, die von einem lizenzierten Benutzer organisiert werden. |

## <a name="how-to-update-licenses"></a>Aktualisieren von Lizenzen

Sie haben vier Möglichkeiten, Ihre Lizenzen zu aktualisieren:

- Lizenzupdate für einzelne Benutzer über Microsoft 365 Admin Center
- Massenaktualisierung von Benutzerlizenzen über Microsoft 365 Admin Center
- Massenaktualisierung von Benutzerlizenzen mithilfe eines PowerShell-Skripts
- Massenaktualisierung von Benutzerlizenzen mithilfe der gruppenbasierten Azure-Lizenzierung

# <a name="option-1-single-user-in-admin-center"></a>[Option 1: Einzelner Benutzer im Admin Center](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Option 1: Lizenzupdate für einzelne Benutzer über Microsoft 365 Admin Center

Um einen einzelnen Benutzer zu aktualisieren, können Sie die Microsoft 365 Admin Center verwenden.

1. Wechseln Sie zu [admin.microsoft.com](https://admin.microsoft.com/) , und melden Sie sich mit den Anmeldeinformationen des Mandantenadministrators an.
1. Navigieren Sie zu **"Aktive Benutzer**"**,** >  und wählen Sie den gewünschten Benutzer aus.
1. Wählen Sie auf der Listensymbolleiste " **Produktlizenzen verwalten** " aus.
1. Deaktivieren Sie auf dem Bildschirm **"Lizenzen und Apps** " die Business Voice-Lizenz.
    > [!IMPORTANT]
    > Speichern Sie die Änderungen noch nicht. Wenn Sie Änderungen speichern, ohne die neuen Lizenzen hinzuzufügen, wird die Bereitstellung des Benutzerkontos aufgehoben, und die Telefonnummer wird nicht zugewiesen.
1. Nachdem Sie die Auswahl von Business Voice deaktiviert haben, überprüfen Sie die neuen Microsoft Teams-Lizenzen für Telefon- und Audiokonferenzen.
1. Jetzt können Sie Ihre Änderungen sicher speichern, indem Sie " **Änderung speichern"** auswählen.

Die Lizenzen des Benutzers werden aktualisiert und sollten sich nicht auf die Dienstverfügbarkeit auswirken.

# <a name="option-2-bulk-users-in-admin-center"></a>[Option 2: Massenbenutzer im Admin Center](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Option 2: Massenaktualisierung der Benutzerlizenz über Microsoft 365 Admin Center

Um die Lizenzen mehrerer Benutzer massenhaft zu aktualisieren, können Sie die Microsoft 365 Admin Center verwenden. Die ausgewählten Benutzer haben dieselbe Lizenzplanzuweisung.

1. Wechseln Sie zu [admin.microsoft.com](https://admin.microsoft.com/) , und melden Sie sich mit den Anmeldeinformationen des Mandantenadministrators an.
1. Navigieren Sie zu **"Aktive Benutzer**"**,** >  und wählen Sie alle gewünschten Benutzer aus.  
1. Wählen Sie auf der Listensymbolleiste " **Produktlizenzen verwalten** " aus.
1. Wählen Sie in der Eingabeaufforderung **"Was möchten Sie mit den Lizenzen für diese Benutzer tun?"** die Option **"Ersetzen: Zuweisung vorhandener Lizenzen aufheben" aus, und weisen Sie neue zu** .
    > [!IMPORTANT]
    > Mit der Option **"Ersetzen"** werden alle vorhandenen Lizenzen für die ausgewählten Benutzer entfernt.  Daher müssen Sie den gewünschten Lizenzierungsstatus für Benutzer auswählen, einschließlich aller anderen verwendeten Lizenzen, z. B. Microsoft 365 Business Premium.
    >
    > Wenn die ausgewählten Benutzer über unterschiedliche Basislizenzkonfigurationen verfügen, werden sie mit Ihren ausgewählten Lizenzen überschrieben, was sich auf andere Bereiche von Microsoft 365 auswirken kann.
    >
    > Für Mandanten mit einem gemischten Lizenzsetup empfehlen wir die Verwendung der Option "Massenaktualisierung" mit einem PowerShell-Skript.For tenants with a mixed license setup, we recommend using the [bulk update option with a PowerShell script](#option-3-bulk-user-license-update-using-a-powershell-script).
1. Deaktivieren Sie auf dem Bildschirm **"Lizenzen und Apps** " die Business Voice-Lizenz.
    > [!IMPORTANT]
    > Speichern Sie die Änderungen noch nicht. Wenn Sie Änderungen speichern, ohne die neuen Lizenzen hinzuzufügen, werden die Konten für die ausgewählten Benutzer aufgehoben und die Telefonnummer nicht zugewiesen.
1. Nachdem Sie die Auswahl von Business Voice deaktiviert haben, überprüfen Sie die neuen Microsoft Teams-Lizenzen für Telefon- und Audiokonferenzen.
1. Jetzt können Sie Ihre Änderungen sicher speichern, indem Sie " **Änderung speichern"** auswählen.
  Die Lizenzen der Benutzer werden aktualisiert und sollten sich nicht auf die Dienstverfügbarkeit auswirken.

# <a name="option-3-bulk-users-via-powershell"></a>[Option 3: Massenbenutzer über PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Option 3: Massenaktualisierung von Benutzerlizenzen mithilfe eines PowerShell-Skripts

Das Ersetzen des Business Voice-Lizenzplans durch ein PowerShell-Skript ist eine effiziente Lösung für die meisten Szenarien.  

Um diese Methode zu verwenden, führen Sie die folgenden allgemeinen Schritte aus:

1. Rufen Sie die mandantenspezifischen Lizenzplan-IDs Ihrer aktuellen Business Voice-Lizenzen ab.
1. Rufen Sie die mandantenspezifischen IDs Ihrer neuen Microsoft Teams-Lizenzpläne für Telefon- und Audiokonferenzen ab.
1. Überprüfen Sie, ob die neuen Lizenzpläne dieselben Dienstpläne haben wie die aktuelle Business Voice-Lizenz.
1. Suchen Sie Mandantenbenutzer, die für Business Voice lizenziert sind (oder ändern Sie das Skript so, dass es einen Filter enthält, um bei Bedarf eine Teilmenge von Benutzern auszuwählen).
1. Aktualisieren Sie die Lizenzkonfiguration der Benutzer mit Teams-Telefon- und Audiokonferenzplänen.

> [!IMPORTANT]
> Das bereitgestellte Skript ist ein Codebeispiel. Das Skript sollte nicht unverändert kopiert und in einem Produktionsmandanten ohne Tests, Überprüfungen und Anpassungen für Ihre spezifische Umgebung ausgeführt werden.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Massenaktualisierung von Lizenzen mithilfe von PowerShell

1. Installieren und importieren Sie das AzureAD PowerShell-Modul.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Stellen Sie eine Verbindung mit Ihrem Microsoft 365-Mandanten her, und geben Sie die Anmeldeinformationen des Mandantenadministrators an.

    ```powershell
    Connect-AzureAD
    ```

1. Verwenden Sie das folgende Befehlslet, um alle Lizenzpakete im Mandanten auflisten.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Verwenden Sie die folgende Tabelle, um den Business Voice-Add-On-Lizenzplan zu identifizieren, der ersetzt wird.

    | SKU-Code | Lizenztyp |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Business Voice mit Anrufplan – Kanada |
    | BUSINESS_VOICE | Business Voice mit Anrufplan – Vereinigtes Königreich |
    | BUSINESS_VOICE_MED2_TELCO | Business Voice mit Anrufplan – USA |
    | BUSINESS_VOICE_DIRECTROUTING | Business Voice ohne Anrufplan |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Business Voice ohne Anrufplan – USA |

    > [!NOTE]
    > Das in diesem Dokument bereitgestellte Skript geht davon aus, dass Sie einen einzelnen SKU-Code für Business Voice in Ihrem Mandanten haben.  
    >
    > Wenn Sie über mehrere Business Voice-SKUs verfügen, müssen Sie das Skript anpassen oder mehrmals ausführen, einmal für jeden SKU-Code.

1. Erstellen Sie eine PowerShell-Variable mit dem Namen `$skuSourceBV`.
    1. Stellen Sie sicher, dass Sie die Bezeichnung durch den `SkuPartNumber` Business Voice SKU-Code Ihres Mandanten ersetzen.
    1. In diesem Beispiel verwenden wir den `BUSINESS_VOICE_MED2_TELCO` SKU-Code.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Verwenden Sie die folgende Tabelle, um Ihre neuen SKU-Codes für Microsoft Teams-Telefon- und -Audiokonferenzlizenzen zu identifizieren.

    | SKU-Code | Lizenztyp |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Teams Telefon mit Anrufplan |
    | MCOEV | Teams Telefon Standard (Kein Anrufplan) |
    | MCOMEETADV | Audiokonferenzen |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Microsoft Teams Audiokonferenz Wählen Sie "Ausgehend" aus. |

1. Erstellen Sie PowerShell-Variablen zum Speichern der eindeutigen SKU-Codes für Telefon- und Audiokonferenzen in Teams.
    1. Stellen Sie sicher, dass Sie die `SkuPartNumber` Bezeichnung durch die SKU-Codes ersetzen, die Sie in Ihrem Mandanten zur Verfügung haben.
    1. In diesem Beispiel verwenden wir die Codes und `MCOMEETADV` SKU`MCOTEAM_ESSENTIALS`.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Führen Sie dieses Skript aus, um die erforderlichen Serviceplandaten aus der Quell-SKU in eindeutigen Objekten zu sammeln.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Bevor Sie fortfahren, überprüfen Sie, ob die Quell-SKU (Business Voice) und die Ziel-SKUs (Teams Phone and Audio Conferencing) die gleichen Servicepläne enthalten.
    1. Ein Konflikt kann eine Lizenzänderung auslösen, die die Sprach- und Audiokonferenzdienste der Benutzer stören könnte.
    2. Erstellen Sie Variablen, um zu überprüfen, ob alle Dienstpläne in der Quell-SKU durch denselben Zieldienstplan ersetzt werden.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Wenn in der Business Voice-Quelllizenz kein Anrufplan enthalten ist, überprüfen Sie nicht danach.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Überprüfen Sie, ob alle Dienstpläne in der Quell-SKU über einen übereinstimmenden Serviceplan in der Ziel-SKU verfügen.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. Wenn in der Ziel-SKU ein Dienstplan fehlt, können Sie die Dienstverfügbarkeit für Benutzer unterbrechen, und Ihr Skript sollte die Verarbeitung beenden.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Wenn alles gut aussieht, bereiten Sie PowerShell-Objekte vor, um die Aktualisierungsvorgänge für Benutzerobjekte auszuführen. Verwenden Sie dafür das `AssignedLicenses` Objekt.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. Rufen Sie als Nächstes die Liste der Benutzer ab, denen die Business Voice-Lizenzen zugewiesen sind, und speichern Sie sie in einer Liste mit dem Namen `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. Führen Sie nun mithilfe der neuen Benutzerliste eine Aktualisierungsaktivität aus, um die Business Voice-Lizenzen zu entfernen und die Microsoft Teams-Lizenzen für Telefon- und Audiokonferenzen mithilfe des ``$LicensesToUpdate`` zuvor erstellten Objekts hinzuzufügen.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Wenn Sie nicht über genügend verfügbare Microsoft Teams-Telefon- und/oder Audiokonferenzlizenzen verfügen, um Business Voice zu ersetzen, erhalten Sie die Fehlermeldung **"Abonnement mit SKU-GUID" hat** während der Benutzerzuweisung keine verfügbare Lizenz, sobald der Lizenzpool erschöpft ist.

### <a name="full-script"></a>Vollständiges Skript

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Option 4: Massenbenutzer mit gruppenbasierter Azure-Lizenzierung](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Option 4: Massenaktualisierung von Benutzerlizenzen mithilfe der gruppenbasierten Azure-Lizenzierung

Mit der gruppenbasierten Azure-Lizenzverwaltung können Sie Abonnements und Dienstpläne einer Gruppe zuweisen.

Diese Methode stellt Folgendes sicher:

- Lizenzen werden allen Mitgliedern der Gruppe zugewiesen.
- Allen neuen Mitgliedern, die der Gruppe beitreten, werden die entsprechenden Lizenzen zugewiesen.
- Wenn Mitglieder aus der Gruppe entfernt werden, werden auch diese Lizenzen entfernt.

Sie müssen die [Lizenzanforderungen für die gruppenbasierte Lizenzierung](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) überprüfen.

> [!NOTE]
> Für diese Methode müssen die Lizenzupdates in einem einzigen Schritt verarbeitet werden.
>
> Es wird empfohlen, eine Liste der vorhandenen Gruppen zu kompilieren, denen Business Voice-Lizenzen zugewiesen sind, zuerst eine kleine Testbenutzergruppe auszuwählen und die Lizenzplanzuweisung durch die bevorzugten neuen Lizenzpläne zu ersetzen.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Massenaktualisierung von Lizenzen mithilfe der gruppenbasierten Lizenzierung

1. Wechseln Sie zu [portal.azure.com](https://portal.azure.com) , und melden Sie sich mit Administratoranmeldeinformationen an.
1. Wechseln Sie zu **Azure Active Directory** , und wählen Sie im linken Menü **"Lizenzen" aus**.
1. Um zu überprüfen, welchen Gruppen Business Voice-Lizenzen zugewiesen sind, wählen Sie **"Alle Produkte** " und dann den Business Voice-Plan aus.
1. Wählen Sie **lizenzierte Gruppen** oder **lizenzierte Benutzer** aus. Die Liste der lizenzierten Gruppen befindet sich im rechten Bereich.
1. Wählen Sie den Gruppennamen aus, um die Gruppenzuweisungsdetails zu öffnen.
1. Wählen Sie **"Aufgaben"** aus, um die dieser Gruppe zugewiesenen Lizenzen zu ändern.
1. Aktivieren Sie die Kontrollkästchen vor den Lizenzplänen, die Sie erworben haben, um Business Voice zu ersetzen.
1. Deaktivieren Sie das Kontrollkästchen vor dem Microsoft 365 Business Voice Lizenzplan.
1. Klicken Sie auf **Speichern**.
1. Kehren Sie zur Gruppe zurück, indem Sie den Gruppennamen auswählen. Es wird ein Banner mit dem Hinweis angezeigt, dass **Lizenzänderungen ausstehen**.
1. Wählen Sie **"Erneut verarbeitet"** aus, um die Aktualisierung der Lizenzzuweisung zu erzwingen.

---

## <a name="validate-user-license-updates"></a>Überprüfen von Benutzerlizenzupdates

Überprüfen Sie nach Abschluss der ausgewählten Methode, ob die Benutzerlizenzen ordnungsgemäß aktualisiert wurden.

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com), und melden Sie sich mit Administratoranmeldeinformationen an.
1. Navigieren Sie zu **"Aktive Benutzer"****,** >  und wählen Sie einen Testbenutzer aus.
1. Wählen Sie auf der Symbolleiste " **Produktlizenzen verwalten** " aus.
1. Überprüfen Sie auf dem Bildschirm **"Lizenzen und Apps** ", welche Lizenzen sie ihnen zugewiesen haben.

Wenn allen Zielbenutzern die richtigen Lizenzen zugewiesen sind, haben Sie die Aktualisierung Ihrer Business Voice-Lizenzen auf Microsoft Teams-Lizenzen für Telefon- und Audiokonferenzen abgeschlossen.
