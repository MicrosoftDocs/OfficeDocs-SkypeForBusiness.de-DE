---
title: Übersicht über Loop-Komponenten in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Loop-Komponenten in Teams verwalten.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e0b9c5a7ffef07a1d9245d2b1266a071b4ee0c2
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795054"
---
# <a name="overview-of-loop-components-in-teams"></a>Übersicht über Loop-Komponenten in Teams

Loop-Komponenten im Teams-Chat bieten eine neue Möglichkeit, gemeinsam Ideen zu entwickeln, zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente – z. B. eine Tabelle, eine Aufgabenliste oder einen Absatz –, in der jede Person in Ihrem Chat Inline-Bearbeitungen vornehmen und Änderungen live anzeigen kann. 

> [!Note]
> Loop-Komponenten sind das erste Feature der [Microsoft Loop-App](https://www.microsoft.com/en-us/microsoft-loop), das in Teams verfügbar gemacht wird. 

**Erledigen Sie Aufgaben gemeinsam schneller.** Erstellen Sie eine Agenda per Crowdsourcing, verfolgen Sie die Aktionselemente einer Gruppe, oder machen Sie sich gemeinsam Notizen. Dies sind nur einige Szenarien, die mit Loop-Komponenten vereinfacht werden.

**Geben Sie Komponenten frei.** In diesem Release können Sie Loop-Komponenten in verschiedenen Teams-Chats freigeben. Empfänger können von überall aus Änderungen vornehmen und Updates sofort anzeigen, unabhängig davon, wo die Änderungen vorgenommen wurden.

**Im Chat starten, von dort aus erstellen.** Jede Komponente, die Sie im Teams-Chat erstellen, wird automatisch in einer Datei in OneDrive gespeichert. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei auf Office.com wechseln, wo Sie über einen größeren visuellen Platz zum Bearbeiten verfügen und beliebig viele Komponenten hinzufügen können.

Informationen zu Administratoreinstellungen für Loop-Komponenten in Teams finden Sie unter [Verwalten von Loop-Komponenten in SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar für Teams-Apps unter Windows, Mac, Linux, iOS und Android.

## <a name="loop-components-and-fluid-files"></a>Loop-Komponenten und FLUID-Dateien

Schleifenkomponenten, die in Teams erstellt wurden, werden von einer .fluid-Datei (wird in naher Zukunft in ".loop" geändert) gesichert, die im OneDrive des Erstellers gespeichert ist. Loop-Komponenten (FLUID-Dateien), die in OneDrive als Datei hinterlegt werden können, lassen sich von Benutzern so einfach wie jedes Office-Dokument erstellen, entdecken und verwalten. 

## <a name="how-are-fluid-files-stored"></a>Wie werden FLUID-Dateien gespeichert?

FLUID-Dateien werden auf Office.com und in OneDrive angezeigt, z. B. in den Bereichen „Zuletzt verwendet“ und „Empfohlen“. Benutzer können in FLUID-Dateien von Office.com und OneDrive nach Inhalten suchen. FLUID-Dateien von OneDrive können auf frühere Versionen zurückgesetzt werden. Zum Erstellen von Loop-Komponenten müssen Chatteilnehmer über ein OneDrive-Konto verfügen. Ohne ein gültiges OneDrive-Konto können Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern mit einem gültigen OneDrive-Konto erstellt wurde, aber keine eigene erstellen. 

Das Verschieben einer FLUID-Datei von OneDrive auf eine SharePoint-Website führt dazu, dass die Livekomponente im Teams-Chat nicht geladen werden kann.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?

Die OneDrive-Aufbewahrungsrichtlinien gelten für FLUID-Dateien genauso wie für andere vom Benutzer erstellte Inhalte.

## <a name="how-are-fluid-files-shared"></a>Wie werden FLUID-Dateien freigegeben?

Loop-Komponenten können in den Teams-Chat eingefügt oder aus einem Chat in einen anderen kopiert werden. (Loop-Komponenten werden in Kanälen noch nicht unterstützt.) Standardmäßig gelten die vorhandenen Berechtigungen der Organisation, aber Benutzer können die Berechtigungen vor dem Senden ändern, um sicherzustellen, dass jeder Zugriff hat.

Beim Öffnen von Komponenten aus dem Teams-Chat auf Office.com stehen Freigabefunktionen am oberen Rand des Fensters zur Verfügung, ähnlich den Freigabeoptionen, die für andere Office-Dokumente angeboten werden.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Was geschieht, wenn eine FLUID-Datei beschädigt wird?

Mit dem Versionsverlauf können Sie frühere Versionen der Datei überprüfen, wiederherstellen oder kopieren.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Welche Apps können FLUID-Dateien öffnen und bearbeiten?

FLUID-Dateien können nur als Links wie z. B. Office.com in Ihrem Browser und als Loop-Komponenten im Teams-Chat geöffnet werden. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder auf OneDrive oder SharePoint hochzuladen.

## <a name="does-fluid-files-support-ediscovery"></a>Unterstützen FLUID-Dateien eDiscovery?

FLUID-Dateien sind auffindbar, verfügen aber über eingeschränkte eDiscovery-Workflowunterstützung. Derzeit werden FLUID-Dateien auf dem OneDrive des Erstellers gespeichert und stehen für die Suche und Sammlung in eDiscovery (Standard) und eDiscovery (Premium) zur Verfügung. Sie werden jedoch nicht in der Vorschau gerendert, und das Exportformat für die Überprüfung kann von vorhandenen Tools nicht verwendet werden. Um die exportierten Inhalte anzuzeigen, laden Sie sie auf ein beliebiges OneDrive hoch. Bei Bedarf können Sie diese Funktionen vorübergehend deaktivieren, wie im Abschnitt [Einstellungsverwaltung](/sharepoint/manage-loop-components#settings-management) beschrieben.

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Wenn Loop über den Administratorschalter deaktiviert ist, wie sieht die Benutzeroberfläche aus?

Wenn Sie diese Erfahrungen deaktivieren, wie im Abschnitt ["Einstellungsverwaltung"](/sharepoint/manage-loop-components#settings-management) beschrieben, gelten die folgenden Änderungen an der Oberfläche:

- Der Einstiegspunkt zum Erstellen/Einfügen in Teams-Nachrichten wird ausgeblendet. Benutzer können keine neuen FLUID-Dateien erstellen.
- Vorhandene Nachrichten, die zuvor als interaktive Loop-Komponente gerendert hätten, werden stattdessen als Link "Loop-Komponente" gerendert. In Teams werden keine interaktiven Inhalte angezeigt.
- Wenn ein Endbenutzer auf den Link "Loop-Komponente" klickt oder in OneDrive for Business zu einer FLUID-Datei navigiert und zum Öffnen klickt, wird die Datei auf einer separaten Browserregisterkarte geöffnet. Endbenutzer können die Datei weiterhin bearbeiten.

## <a name="known-issues"></a>Bekannte Probleme

- Bei Mandantenstandarddateiberechtigungen, die auf *bestimmte Personen* festgelegt sind (nur die Vom Benutzer angegebenen Personen), erfordert das Kopieren des Links in die Loop-Komponente und das Einfügen in einen anderen Chat, dass der Absender das Dialogfeld "Berechtigungen" verwendet und die Empfänger in der Option "Bestimmte Personen" hinzufüge, um den Zugriff ordnungsgemäß zu gewähren.
- Wenn die Standarddateiberechtigungen des Mandanten auf *Bestimmte Personen* festgelegt sind (nur die vom Benutzer angegebenen Personen), muss der Absender zum Erstellen einer Livekomponente in einem Gruppenchat mit mehr als 20 Mitgliedern die Berechtigungsoptionen für die Komponente manuell auswählen.
- Bei der Suche nach Loop-Komponenten über die Teams-Suchfunktion wird ein Link zur Komponente in office.com zurückgegeben, nicht zur Chatnachricht selbst.
- Loop-Komponenten sind in Verbundchats deaktiviert.
- Gäste können nicht an einer Livekomponente zusammenarbeiten, die über den Firmenfreigabelink für sie freigegeben wird. Legen Sie Die Berechtigungen auf **Personen fest, die sich derzeit in diesem Chat** befinden, um Komponenten für Gäste freizugeben.
- Loop-Komponenten werden in Teams-Kanälen nicht unterstützt.
- Loop-Komponenten im Chat werden nur dann nicht geladen, wenn die Datei in eine andere Bibliothek verschoben wurde. Wenn die Datei in einen anderen Ordner verschoben wird, wird sie weiterhin im Chat geladen.
