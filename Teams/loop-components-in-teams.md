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
ms.openlocfilehash: 3f9ca97a0088c703dc482d69406a9e9c2c8b2a22
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043373"
---
# <a name="overview-of-loop-components-in-teams"></a>Übersicht über Schleifenkomponenten in Teams

Endloskomponenten in Teams bieten eine neue Möglichkeit, gemeinsam Ideen zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente, z. B. eine Tabelle, Aufgabenliste oder einen Absatz, in der jeder Chat inline bearbeiten und änderungen anzeigen kann, während sie vorgenommen werden. 

> [!Note]
> Loopkomponenten sind das erste Feature der [Microsoft Loop-App](https://www.microsoft.com/en-us/microsoft-loop), das in ihrer Teams. 

**Erledigen Sie Aufgaben schneller zusammen.** Sie können eine Tagesordnung aus der Menge stammen lassen, die Aktionselemente einer Gruppe nachverfolgen oder gemeinsam Notizen machen. Dies sind nur einige wenige Szenarien, die mit Loop-Komponenten einfacher gemacht werden.

**Teilen von Komponenten.** In dieser Version können Sie Loop-Komponenten in verschiedenen Chats Teams teilen. Empfänger können von überall aus bearbeiten und Aktualisierungen sofort sehen, unabhängig davon, wo die Änderungen vorgenommen wurden.

**Starten Sie im Chat, erstellen Sie von dort aus.** Jede Komponente, die Sie Teams Chat erstellen, wird automatisch in einer Datei in OneDrive. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei wechseln, in der Sie über einen größeren visuellen Bereich zum Bearbeiten verfügen und so viele Komponenten hinzufügen können, wie Sie möchten.

Informationen zu den Administratoreinstellungen für Endloskomponenten in Teams finden Sie unter [Verwalten von Schleifenkomponenten in SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar für Teams-Apps Windows, Mac, Linux, iOS und Android.

## <a name="loop-components-and-loop-files"></a>Endloskomponenten und Loopdateien

In einem -Teams erstellte Schleifenkomponenten werden durch eine LOOP-Datei gesichert, die in der Datei des Erstellers OneDrive. Als Datei in OneDrive bedeutet dies, dass Benutzer Endloskomponenten (Loopdateien) genauso einfach erstellen, entdecken und verwalten können wie jedes Office Dokument. Loopdateien funktionieren mit Daten-Governance-Features wie eDiscovery, Überwachung, Berichterstellung und gesetzliche Lücke.

## <a name="how-are-loop--files-stored"></a>Wie werden LOOP-Dateien gespeichert?

LOOP-Dateien werden auf Office.com und OneDrive angezeigt, z. B. in den Bereichen Zuletzt verwendet und Empfohlen. Benutzer können in Dateien mit der Datei "Office.com" und "OneDrive" nach Inhalten OneDrive. LOOP-Dateien können aus dem -OneDrive in früheren OneDrive. Um Komponenten für Schleifen zu erstellen, müssen die Chatteilnehmer über ein OneDrive verfügen. Ohne ein gültiges OneDrive-Konto können die Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern erstellt wurde, die über ein gültiges OneDrive-Konto verfügen, aber keine eigene Komponente erstellen. 

Das Verschieben einer Loopdatei von OneDrive auf eine SharePoint-Website führt dazu, dass die Livekomponente im Chat Teams wird.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?

OneDrive Aufbewahrungsrichtlinien gelten für Loopdateien genauso wie für andere vom Benutzer erstellte Inhalte.

## <a name="how-are-loop-files-shared"></a>Wie werden LOOP-Dateien freigegeben?

Endloskomponenten können in einem Chat Teams oder aus einem Chat in einen anderen kopiert werden. (Loopkomponenten werden in Kanälen noch nicht unterstützt.) Sie werden standardmäßig auf die vorhandenen Berechtigungen der Organisation festgelegt, die Benutzer können jedoch vor dem Senden Berechtigungen ändern, um sicherzustellen, dass jeder Zugriff hat.

Das Öffnen von Komponenten aus Teams-Chats in Office.com bietet am oberen Rand des Fensters Freigabefunktionen, ähnlich wie die Freigabeoptionen, die für andere Office werden.

## <a name="what-if-a-loop-file-becomes-corrupted-or-damaged"></a>Was passiert, wenn eine LOOP-Datei beschädigt oder beschädigt wird?

Der Versionsverlauf ermöglicht es Ihnen, frühere Versionen der Datei zu überprüfen und zu kopieren.

## <a name="what-apps-can-open-and-edit-loop-files"></a>Welche Apps können Loopdateien öffnen und bearbeiten?

Loopdateien können nur als Links in Ihrem Browser, z. B. Office.com, und als Loop-Komponenten in Teams geöffnet werden. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder in den OneDrive oder SharePoint.

## <a name="known-issues"></a>Bekannte Probleme

- Loopkomponenten in Chats können nicht mithilfe von Office-App unter Android Teams bearbeitet werden.
- Wenn die Standarddateiberechtigungen des Mandanten auf Bestimmte *Personen (nur* die vom Benutzer angegebenen Personen) festgelegt sind und der Absender beim Erstellen einer  Komponente einige Benutzer aus der Liste Bestimmte Personen im Berechtigungsdialogfeld entfernt, haben diese Benutzer möglicherweise weiterhin Zugriff auf den Inhalt.
- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte *Personen (nur* vom Benutzer festgelegte Personen) festgelegt sind, muss der Absender beim Kopieren des Links in die Livekomponente und beim Einfügen in einen anderen Chat das Dialogfeld "Berechtigungen" verwenden und die Empfänger zur Option Bestimmte Personen hinzufügen, damit der Zugriff ordnungsgemäß gewährt wird.
- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte *Personen (nur* vom Benutzer festgelegte Personen) festgelegt sind, muss der Absender beim Erstellen einer Livekomponente in einem Gruppenchat mit mehr als 20 Mitgliedern die Berechtigungsoptionen für die Komponente manuell auswählen.
- Bei der Suche nach Komponenten für Schleifen Teams in der Suchfunktion wird ein Link zur Komponente in office.com und nicht die Chatnachricht selbst angezeigt.
- Endloskomponenten sind in Partnerchats deaktiviert.
- B2B-Gäste können nicht an einer Livekomponente zusammenarbeiten, die über den Freigabelink des Unternehmens für sie freigegeben wird. Legen Sie Berechtigungen auf **Personen, die sich derzeit in diesem Chat befindet** , zum Freigeben von Komponenten für B2B-Gäste ein.
- Loopkomponenten werden in Teams nicht unterstützt.
- Endloskomponenten in Chats werden nicht nur geladen, wenn die Datei in eine andere Bibliothek verschoben wurde. Wenn die Datei in einen anderen Ordner verschoben wird, wird sie weiterhin im Chat geladen.
