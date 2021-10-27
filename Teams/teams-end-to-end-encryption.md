---
title: End-to-End-Verschlüsselung für Microsoft Teams
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 10/23/2021
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Erfahren Sie mehr über erweiterte Verschlüsselungsfunktionen in Microsoft Teams, und verwalten Sie die End-to-End-Verschlüsselung mit dem Teams Admin Center und Microsoft PowerShell.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdc626510a180185cae699106c1420880ea55e73
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579699"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls-public-preview"></a>Verwenden der End-to-End-Verschlüsselung für 1:1-Anrufe in Microsoft Teams (öffentliche Vorschau)

> [!IMPORTANT]
> Das Teams-Dienstmodell und sein Verschlüsselungssupport können sich ändern, um die Benutzererfahrung zu verbessern. Der Dienst veraltet beispielsweise regelmäßig Chiffriersammlungen, die nicht mehr als sicher gelten. Solche Änderungen würden vorgenommen, um die Sicherheit und Vertrauenswürdigkeit von Teams zu gewährleisten. Darüber hinaus sind alle Kundeninhalte in Microsoft-Rechenzentren verschlüsselt. Weitere Informationen über Verschlüsselungsebenen in Microsoft 365 finden Sie unter [Verschlüsselung in Microsoft 365](/microsoft-365/compliance/encryption).

Die End-to-End-Verschlüsselung (oder E2EE) wird durchgeführt, wenn Inhalte verschlüsselt werden, bevor sie gesendet und nur vom vorgesehenen Empfänger entschlüsselt werden. Bei der End-to-End-Verschlüsselung sind nur die beiden Endpunktsysteme an der Verschlüsselung und Entschlüsselung der Anrufdaten beteiligt. Keine andere Partei, einschließlich Microsoft, hat Zugriff auf die entschlüsselte Unterhaltung.

Mit dieser öffentlichen Vorschauversion führen wir E2EE für ungeplante 1:1-Anrufe ein. Nur der Echtzeitmedienfluss, d. h. Video- und Sprachdaten, für 1:1-Teams-Anrufe wird End-to-End verschlüsselt. Beide Parteien müssen diese Einstellung aktivieren, um die End-to-End-Verschlüsselung zu aktivieren. [Verschlüsselung in Microsoft 365](/microsoft-365/compliance/encryption) schützt Chat-, Dateifreigabe-, Anwesenheits- und andere Inhalte im Anruf.

Wenn Sie die End-to-End-Verschlüsselung nicht aktivieren, sichert Teams weiterhin einen Anruf oder eine Besprechung mittels Verschlüsselung basierend auf Branchenstandards. Daten, die bei Anrufen ausgetauscht werden, sind während der Übertragung und im Ruhezustand immer sicher. Weitere Informationen finden Sie unter [Medienverschlüsselung für Teams](teams-security-guide.md#media-encryption).

Während eines verschlüsselten End-to-End-Anrufs sichert Teams die folgenden Features:

- Audio

- Video

- Bildschirmübertragung

Die folgenden erweiterten Features sind während eines E2EE-Anrufs nicht verfügbar:

- Liveuntertitel und Transkription

- Anrufweiterleitung

- Anrufzusammenführung

- Anruf parken

- Ankündigen, dann weiterleiten

- Anrufbegleiter und Weiterleitung auf ein anderes Gerät

- Hinzufügen eines Teilnehmers

- Aufzeichnung läuft

Wenn Ihre Organisation die Complianceaufzeichnung verwendet, ist die End-to-End-Verschlüsselung ebenfalls nicht verfügbar. Weitere Informationen zur Unterstützung von Complianceaufzeichnungen durch Teams finden Sie unter [Einführung in richtlinienbasierte Teams-Aufzeichnungen für Anrufe und Besprechungen](teams-recording-policy.md).

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Konfigurieren der End-to-End-Verschlüsselung für Microsoft Teams

Führen Sie diese Aufgaben aus, damit Ihre Benutzer verschlüsselte End-to-End-Anrufe tätigen können.

- Aktivieren Sie die End-to-End-Verschlüsselung für Ihre Organisation, indem Sie eine oder mehrere Richtlinien erstellen, die definieren, wer die End-to-End-Verschlüsselung verwenden kann. Bevor Sie beginnen, stellen Sie sicher, dass Ihrem Geschäfts-, Schul- oder Unikonto die Teams- oder globale Administratorrolle zugewiesen wurde. Weitere Informationen finden Sie unter [Verwalten von Teams mittels Microsoft Teams-Administratorrollen](using-admin-roles.md). Wenn Sie bereit sind, E2EE einzurichten, können Sie das Teams Admin Center oder Microsoft PowerShell verwenden.

- Aktivieren Sie verschlüsselte End-to-End-Anrufe in den Teams-Einstellungen auf Ihrem Gerät. Jeder Benutzer muss diese Aufgabe ausführen, aber er muss sie nur auf einem Gerät ausführen. Teams synchronisiert diese Einstellung für jeden Benutzer über unterstützte Endpunkte hinweg. Anweisungen finden Sie unter [Verwenden der End-to-End-Verschlüsselung für Teams-Anrufe](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Konfigurieren der End-to-End-Verschlüsselung mithilfe des Teams Admin Centers

Die globale, organisationsweite Standardrichtlinie gibt an, dass die End-to-End-Verschlüsselung deaktiviert ist. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Um die End-to-End-Verschlüsselung zu aktivieren, erstellen Sie eine neue Verschlüsselungsrichtlinie, oder passen Sie die globale Standardrichtlinie an. Führen Sie die folgenden Schritte aus, um die End-to-End-Verschlüsselung mithilfe des Teams Admin Centers zu aktivieren.

1. Melden Sie sich mit einem Geschäfts-, Schul- oder Unikonto, dem die Teams- oder globale Administratorrolle zugewiesen wurde, beim [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) an.

2. Wechseln Sie zu **Andere Einstellungen** > **Erweiterte Verschlüsselungsrichtlinien**.

3. Wählen Sie entweder die Standardrichtlinie aus, oder wählen Sie **Hinzufügen** aus, um eine neue Richtlinie hinzuzufügen und dann die neue Richtlinie zu benennen.

4. Um die End-to-End-Verschlüsselung für Ihre Benutzer zu aktivieren, wählen Sie für die **End-to-End-Anrufverschlüsselung** die Option **Benutzer können sie aktivieren** aus, und dann wählen Sie **Speichern** aus.

   Um die End-to-End-Verschlüsselung zu deaktivieren, wählen Sie **Für alle deaktivieren** aus.

Nachdem Sie die Einrichtung der Richtlinie abgeschlossen haben, weisen Sie die Richtlinie Benutzern, Gruppen oder Ihrem gesamten Mandanten auf die gleiche Weise zu, wie Sie andere Teams-Richtlinien verwalten. Informationen zur Verwendung von Richtlinien in Teams finden Sie unter [Teams mit Richtlinien verwalten](manage-teams-with-policies.md).

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Verwenden von Microsoft PowerShell zum Konfigurieren der End-to-End-Verschlüsselung

Sie können End-to-End-Verschlüsselungsrichtlinien mithilfe von Microsoft PowerShell und dem Teams Admin Center verwalten. Mehrere Cmdlets für die End-to-End-Verschlüsselung sind im Teams PowerShell-Modul enthalten und in der [Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps&preserve-view=true) dokumentiert. Dieser Artikel listet die Cmdlets auf, die Sie verwenden können, und enthält einfache Beispielkonfigurationen. Diese Konfigurationen verwenden die globale Standardrichtlinie. Ihre Organisation erfordert möglicherweise eine komplexere Richtlinienkonfiguration. Vollständige Informationen zu diesen Cmdlets finden Sie in der Cmdlet-Referenz.

PowerShell-Cmdlets für die End-to-End-Verschlüsselung:

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) gibt Informationen zu den erweiterten Teams-Verschlüsselungsrichtlinien in Ihrer Organisation zurück.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) weist einem Benutzer vorhandene erweiterte Verschlüsselungsrichtlinien zu, und hebt deren Zuweisung auf. Verwenden Sie `$NULL`, um die Zuweisung aller Richtlinien zu einem Benutzer aufzuheben.

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) erstellt eine neue erweiterte Teams-Verschlüsselungsrichtlinie.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) löscht eine erweiterte Verschlüsselungsrichtlinie aus Ihrer Organisation. Sie können die globale Standardrichtlinie nicht löschen.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) aktualisiert Werte in einer vorhandenen erweiterten Teams-Verschlüsselungsrichtlinie.

Ihr Geschäfts-, Schul- oder Unikonto benötigt die Teams- oder globale Administratorrolle, um die End-to-End-Verschlüsselung zu konfigurieren.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>So aktivieren Sie die End-to-End-Verschlüsselung für Ihren gesamten Mandanten mithilfe der globalen Richtlinie

Standardmäßig ist die End-to-End-Verschlüsselung deaktiviert. Um die End-to-End-Verschlüsselung für den gesamten Mandanten durch Festlegen der globalen Standardrichtlinie zu aktivieren, führen Sie das Cmdlet [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) wie folgt aus.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

Dabei gilt Folgendes:

- `Global` bedeutet, dass Sie diese Konfiguration über die globale, organisationsweite Standardrichtlinie festlegen.

- `DisabledUserOverride` bedeutet, dass E2EE standardmäßig in Teams deaktiviert ist. Benutzer können die Standardeinstellung jedoch außer Kraft setzen und E2EE in ihren Teams-Einstellungen aktivieren.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>So deaktivieren Sie die End-to-End-Verschlüsselung für Ihren gesamten Mandanten mithilfe der globalen Richtlinie

Standardmäßig ist die End-to-End-Verschlüsselung deaktiviert. Wenn Sie Änderungen an der globalen Richtlinie vorgenommen haben, können Sie die Einstellung wieder ändern, indem Sie das Cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) wie folgt ausführen.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

Dabei gilt Folgendes:

- `Global` bedeutet, dass Sie diese Konfiguration über die globale, organisationsweite Standardrichtlinie festlegen.

- `Disabled` bedeutet, dass Sie E2EE für alle Benutzer deaktivieren. Benutzer können sie in ihren Teams-Einstellungen nicht aktivieren.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>So aktivieren Sie die End-to-End-Verschlüsselung für einen einzelnen Benutzer

Um die End-to-End-Verschlüsselung für einen Benutzer zu aktivieren, führen Sie das Cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) wie folgt aus.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

Dabei gilt Folgendes:

- *`username`* ist der Name des Benutzers.

- *`policyname`* ist der Name, den Sie für die Richtlinie verwenden möchten. Richtliniennamen dürfen keine Leerzeichen enthalten, z. B. ContosoE2EEUserPolicy.

Benutzer müssen in ihren Teams-Einstellungen trotzdem noch verschlüsselte End-to-End-Anrufe aktivieren, bevor sie einen verschlüsselten End-to-End-Anruf tätigen können. Anweisungen finden Sie unter [Verwenden der End-to-End-Verschlüsselung für Teams-Anrufe](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

Zum Beispiel: 

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>So heben Sie die Zuweisung einer End-to-End-Verschlüsselungsrichtlinie zu einem einzelnen Benutzer auf

Einem Benutzer kann jeweils nur eine einzige Verschlüsselungsrichtlinie zugewiesen sein. Wenn Sie die Zuweisung einer Richtlinie zu einem Benutzer aufheben, wird dem Benutzer dann die globale, organisationsweite Standardrichtlinie zugewiesen. Sie können die Zuweisung der Standardrichtlinie nicht aufheben. Um die Zuweisung einer End-to-End-Verschlüsselungsrichtlinie zu einem Benutzer aufzuheben, führen Sie das Cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) wie folgt aus.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>Aktivieren der End-to-End-Verschlüsselung auf Ihrem Gerät

Anweisungen finden Sie unter [Verwenden der End-to-End-Verschlüsselung für Teams-Anrufe](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

## <a name="related-topics"></a>Verwandte Themen

[Die wichtigsten 12 Aufgaben für Sicherheitsteams zur Unterstützung der Arbeit von zu Hause aus](/microsoft-365/security/top-security-tasks-for-remote-work)

[Verwalten von Besprechungseinstellungen in Microsoft Teams](./meeting-settings-in-teams.md)
