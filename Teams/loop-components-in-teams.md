---
title: Übersicht über Schleifenkomponenten in Teams
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
description: Hier erfahren Sie, wie Sie Komponenten für Schleifen in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a43ea4c217e09ad4473513fd21e159bd15c89716
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312447"
---
# <a name="overview-of-loop-components-in-teams"></a>Übersicht über Schleifenkomponenten in Teams

Endloskomponenten in Teams bieten eine neue Möglichkeit, gemeinsam Ideen zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente, z. B. eine Tabelle, Aufgabenliste oder einen Absatz, in der jeder Chat inline bearbeiten und änderungen anzeigen kann, während sie vorgenommen werden. 

> [!Note]
> Loopkomponenten sind das erste Feature der [Microsoft Loop-App](https://www.microsoft.com/en-us/microsoft-loop), das in Ihrer App Teams. 

**Erledigen Sie Aufgaben schneller zusammen.** Sie können eine Tagesordnung aus der Menge stammen lassen, die Aktionselemente einer Gruppe nachverfolgen oder gemeinsam Notizen machen. Dies sind nur einige wenige Szenarien, die mit Loop-Komponenten einfacher gemacht werden.

**Teilen von Komponenten.** In dieser Version können Sie Endloskomponenten in verschiedenen Chats Teams teilen. Empfänger können von überall aus bearbeiten und Aktualisierungen sofort sehen, unabhängig davon, wo die Änderungen vorgenommen wurden.

**Starten Sie im Chat, erstellen Sie von dort aus.** Jede Komponente, die Sie Teams Chat erstellen, wird automatisch in einer Datei in OneDrive. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei wechseln, in der Sie über einen größeren visuellen Bereich zum Bearbeiten verfügen und so viele Komponenten hinzufügen können, wie Sie möchten.

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar für Teams-Apps Windows, Mac, Linux, iOS und Android.

## <a name="loop-components-and-fluid-files"></a>Endloskomponenten und FLUID-Dateien

In einem -Teams erstellte Loopkomponenten werden durch eine FLUID-Datei gesichert, die in der Datei des Erstellers OneDrive. Als Datei in OneDrive bedeutet dies, dass Benutzer endlose Komponenten (FLUID-Dateien) genauso einfach erstellen, entdecken und verwalten können wie jedes Office Dokument. Fluid-Dateien arbeiten mit Daten-Governance-Features wie eDiscovery, Überwachung, Berichterstellung und gesetzliche Erkung.

## <a name="how-are-fluid--files-stored"></a>Wie werden FLUID-Dateien gespeichert?

FLUID-Dateien werden auf Office.com und OneDrive angezeigt, z. B. in den Bereichen Zuletzt verwendet und Empfohlen. Benutzer können über "Office.com" und "E-OneDrive" nach Inhalten in flüssigen Dateien OneDrive. FLUID-Dateien können aus der Datei wiederhergestellt werden, die in früheren OneDrive. Um Komponenten für Schleifen zu erstellen, müssen die Chatteilnehmer über ein OneDrive verfügen. Ohne ein gültiges OneDrive-Konto können die Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern erstellt wurde, die über ein gültiges OneDrive-Konto verfügen, aber keine eigenen erstellen können. 

Das Verschieben einer FLUID-Datei von OneDrive auf eine SharePoint-Website führt dazu, dass die Livekomponente im Chat Teams wird.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?

OneDrive Aufbewahrungsrichtlinien gelten für FLUID-Dateien genauso wie für andere vom Benutzer erstellte Inhalte.

## <a name="how-are-fluid-files-shared"></a>Wie werden FLUID-Dateien freigegeben?

Endloskomponenten können in einem Chat Teams oder aus einem Chat in einen anderen kopiert werden. (Loopkomponenten werden in Kanälen noch nicht unterstützt.) Sie werden standardmäßig auf die vorhandenen Berechtigungen der Organisation festgelegt, die Benutzer können jedoch vor dem Senden Berechtigungen ändern, um sicherzustellen, dass jeder Zugriff hat.

Das Öffnen von Komponenten Teams Chats in Office.com bietet am oberen Rand des Fensters Freigabefunktionen, ähnlich wie die Freigabeoptionen, die für andere Office werden.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Was passiert, wenn eine FLUID-Datei beschädigt wird?

Der Versionsverlauf ermöglicht es Ihnen, frühere Versionen der Datei zu überprüfen und zu kopieren.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Welche Apps können fluide Dateien öffnen und bearbeiten?

FLUID-Dateien können nur als Links in Ihrem Browser, z. B. Office.com, und als Endloskomponenten in Teams geöffnet werden. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder in den OneDrive oder SharePoint.

## <a name="known-issues"></a>Bekannte Probleme

- Endloskomponenten in Chats können nicht mithilfe von Office-App unter Android Teams bearbeitet werden.
- Wenn die Standarddateiberechtigungen des Mandanten auf Bestimmte *Personen (nur* die vom Benutzer angegebenen Personen) festgelegt sind und der Absender beim Erstellen einer  Komponente einige Benutzer aus der Liste Bestimmte Personen im Berechtigungsdialogfeld entfernt, haben diese Benutzer möglicherweise weiterhin Zugriff auf den Inhalt.
- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte *Personen (nur* vom Benutzer festgelegte Personen) festgelegt sind, muss der Absender beim Kopieren des Links in die Livekomponente und beim Einfügen in einen anderen Chat das Dialogfeld "Berechtigungen" verwenden und die Empfänger zur Option Bestimmte Personen hinzufügen, damit der Zugriff ordnungsgemäß gewährt wird.
- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte *Personen (nur* vom Benutzer festgelegte Personen) festgelegt sind, muss der Absender beim Erstellen einer Livekomponente in einem Gruppenchat mit mehr als 20 Mitgliedern die Berechtigungsoptionen für die Komponente manuell auswählen.
- Bei der Suche nach Komponenten für Teams wird ein Link zur Komponente in der office.com und nicht die Chatnachricht selbst zurück.
- Endloskomponenten sind in Partnerchats deaktiviert.
- B2B-Gäste können nicht an einer Livekomponente zusammenarbeiten, die über Personen *in* Ihrer Organisation-Links für sie freigegeben wird, es sei denn, der Mandant legt eine Option für externen Zugriff fest, damit B2B-Gäste dieselbe Zugriffsebene wie Mandantenmitglieder erhalten. Weitere Informationen finden Sie unter [Konfigurieren von B2B-Einstellungen für die externe Zusammenarbeit](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings).
- Loopkomponenten werden in anderen Kanälen Teams unterstützt.
- Endloskomponenten in Chats werden nicht nur geladen, wenn die Datei in eine andere Bibliothek verschoben wurde. Wenn die Datei in einen anderen Ordner verschoben wird, wird sie weiterhin im Chat geladen.
