---
title: Verwalten und Filtern von Microsoft Teams-Gerätekategorien
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: Erfahren Sie, wie Sie Kategorien auf Ihren Microsoft Teams-Geräten verwalten und Filtern können.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f428a40e5a9adf4a53d4b2e12064b90b4ceebe43
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46657098"
---
# <a name="manage-microsoft-teams-device-tags"></a>Verwalten von Microsoft Teams-Gerätekategorien

> [!NOTE]
> Die Möglichkeit zum Hinzufügen von Kategorien zu Geräten wird Microsoft Teams-Kunden in Waves zur Verfügung gestellt. Wenn die Option zum Verwalten von Tags im Team Admin Center nicht angezeigt wird, sind Geräte Tags noch nicht für Ihren Mandanten aktiviert. Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt.

Mithilfe von Geräte Tags in Microsoft Teams können Sie die Geräte, die Sie in Ihrer Organisation bereitgestellt haben, gruppieren, organisieren und einfacher verwalten. Mit dem Microsoft Teams Admin Center können Sie einen oder mehrere Kategorien zu Geräten hinzufügen, Filter verwenden, um Geräte anzuzeigen, die dem von Ihnen angegebenen Tag entsprechen, und dann Aktionen auf den Geräten durchführen, die diese Kategorie aufweisen.

Sie können ein Device-Tag zu mehr als einem Gerätetyp hinzufügen. Wenn Sie jedoch einen Gerätebereich im Admin Center öffnen, werden nur die Geräte dieses Typs zurückgegeben. So können Sie beispielsweise die Kategorie "Unternehmen" sowohl für Telefone als auch für Teams für Chatrooms festlegen. Wenn Sie nach dem "Corporate"-Tag suchen, während Sie sich in **Geräte**  >  -**Smartphones**befinden, werden nur Telefone zurückgegeben. Wenn Sie nach dem "Corporate"-Tag in den **Geräten**  >  **Teams rooms**suchen, werden nur Teams rooms-Geräte zurückgegeben.

Zum Verwalten von Geräte Tags müssen Sie entweder ein globaler Administrator oder ein Team Dienstadministrator sein.

> [!IMPORTANT]
> Geräte Tags werden dem Ressourcenkonto zugewiesen, das bei einem Gerät angemeldet ist. Wenn Sie ein Ressourcenkonto von einem Gerät aus Signieren und es dann zum Anmelden bei anderen Geräten verwenden, werden die Gerätekategorien auf das neue Gerät angewendet.

## <a name="create-remove-or-rename-device-tags"></a>Erstellen, entfernen oder Umbenennen von Gerätekategorien

Mithilfe der Geräte-Tag-Verwaltungskonsole können Sie Folgendes tun:

- Alle Ihre Gerätekategorien anzeigen.
- Erstellen Sie einfach mehrere Gerätekategorien, und weisen Sie Sie dann zu einem späteren Zeitpunkt den Geräten zu. Tags können bis zu 25 Zeichen umfassen.
- Entfernen Sie Gerätekategorien, die nicht mehr benötigt werden. Bevor Sie ein gerätetag entfernen können, müssen Sie es von allen Geräten entfernen, denen es hinzugefügt wurde.
- Umbenennen von Gerätekategorien Wenn Sie ein Device-Tag umbenennen, wird diese Änderung auf allen Geräten widergespiegelt, denen Sie hinzugefügt wurde. Tags können bis zu 25 Zeichen umfassen.

1. Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com
2. Navigieren Sie zu **Geräten** , und wählen Sie dann einen beliebigen Gerätebereich wie **Telefone** aus.
3. Wählen Sie in der oberen rechten Ecke der Seite **Aktionen** aus, und wählen Sie **alle Gerätekategorien** aus.
4. Wenn Sie ein gerätetag erstellen möchten, wählen Sie **+ Hinzufügen**aus, geben Sie einen Wert für das Device-Tag ein, und wählen Sie das Symbol **Speichern** aus.
5. Wenn Sie ein Geräte-Tag entfernen möchten, wählen Sie die Auslassungspunkte neben dem zu entfernenden gerätetag aus, und wählen Sie **Löschen** aus **.**
    > [!NOTE]
    > Wenn Sie versuchen, ein Device-Tag zu entfernen, das zu Geräten hinzugefügt wurde, erhalten Sie eine Meldung, in der Sie gefragt werden, ob Sie es von allen Geräten entfernen möchten. Wenn Sie dies tun möchten und weiterhin das Device-Tag entfernen möchten, wählen Sie **Markierung-Geräte**aus.
6. Wenn Sie ein gerätetag umbenennen möchten, wählen Sie das Auslassungs **Zeichen neben dem** gerätetag aus, das Sie umbenennen möchten, und wählen Sie **Bearbeiten**aus. Geben Sie einen neuen Wert für das Device-Tag ein, und wählen Sie das Symbol **Speichern** aus.

## <a name="add-or-remove-tags-on-a-single-device"></a>Hinzufügen oder Entfernen von Tags auf einem einzelnen Gerät

Wenn Sie einem Gerät Kategorien hinzufügen, können Sie entweder eine vorhandene Kategorie auswählen oder eine neue erstellen. Tags können bis zu 25 Zeichen umfassen.

1. Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com
2. Navigieren Sie zu **Geräten** , und wählen Sie dann den Gerätebereich mit dem Gerät aus, auf dem Sie Kategorien hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben dem Gerät, das Sie hinzufügen oder entfernen möchten, und wählen Sie **Kategorien verwalten** aus.
4. Wenn Sie eine Kategorie hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Kategorienamens, den Sie hinzufügen möchten.
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der Kategorien aus, die zurückgegeben werden.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **" \<tag name> " als neues Tag hinzufügen**aus. Tags können bis zu 25 Zeichen umfassen.
5. Wenn Sie ein Tag entfernen möchten, wählen Sie neben dem zu entfernenden Tag **X** aus.
6. Wiederholen Sie die obigen Schritte, wenn Sie weitere Kategorien hinzufügen oder entfernen möchten.
7. Wählen Sie über **nehmen** aus.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Hinzufügen oder Entfernen von Tags auf mehreren Geräten

Wenn Sie einem Gerät Kategorien hinzufügen, können Sie entweder eine vorhandene Kategorie auswählen oder eine neue erstellen. Tags können bis zu 25 Zeichen umfassen. Wenn Sie eine Kategorie von mehreren Geräten entfernen möchten, müssen Sie den Team Benutzer auswählen, der dem Gerät zugeordnet ist, und das Tag vom Benutzer entfernen.

1. Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com
2. Navigieren Sie zu **Geräten** , und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, für die Sie Kategorien hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben den Geräten, die Sie hinzufügen oder entfernen möchten, und wählen Sie **Kategorien verwalten** aus.
4. Wenn Sie eine Kategorie hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Kategorienamens, den Sie hinzufügen möchten, in **Verwalten von Tags für alle Geräte von Teams-Benutzern** .
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der Kategorien aus, die zurückgegeben werden.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **" \<tag name> " als neues Tag hinzufügen** aus.
5. Wenn Sie eine Kategorie entfernen möchten:
    1. Erweitern **Sie SELECT Teams-Benutzer** .
    2. Erweitern Sie ** \<x> Kategorien** unter dem Namen des Teams-Benutzers, aus dem Sie Kategorien entfernen möchten.
    3. Wählen Sie neben dem zu entfernenden Tag **X** aus.
6. Wiederholen Sie die obigen Schritte, wenn Sie weitere Kategorien hinzufügen oder entfernen möchten.
7. Wählen Sie über **nehmen** aus.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Verwenden von Filtern zum Zurückgeben von Geräten mit einer bestimmten Kategorie

Wenn Sie Ihren Geräten Gerätekategorien hinzugefügt haben, können Sie diese zum Filtern der Geräteliste verwenden, um nur die Geräte zurückzugeben, denen eine bestimmte Kategorie hinzugefügt wurde. Dies kann hilfreich sein, wenn Sie nur alle Geräte in einem bestimmten Raum, alle Geräte eines bestimmten Typs oder alle anderen Kriterien anzeigen möchten, die Sie beim Hinzufügen Ihrer Tags verwendet haben. Sie können auch Massenaktionen auf zurückgegebenen Geräten durchführen, wie etwa das Anwenden von Updates in Waves oder das Festlegen unterschiedlicher Konfigurationsrichtlinien, abhängig von den Gruppen von Geräten, die mithilfe von Gerätekategorien identifiziert werden.

1. Wenn Sie sich beim Microsoft Teams Admin Center anmelden, besuchen Siehttps://admin.teams.microsoft.com
2. Navigieren Sie zu **Geräten** , und wählen Sie dann den Gerätebereich mit den Geräten aus, die Sie filtern möchten.
3. Auswählen des **Filters** -Symbols
4. Wenn Sie nur ein einzelnes Tag angeben möchten, oder wenn Sie Geräte mit allen von Ihnen angegebenen Tags suchen möchten, wählen Sie **alle diese Bedingungen abgleichen**aus.
5. Wenn Sie Geräte suchen möchten, die mit einem oder mehreren Gerätekategorien übereinstimmen, wählen Sie eine **der folgenden Bedingungen** aus.
6. Wählen Sie das **Tag** -Feld aus, und geben Sie dann im Feld **Geben Sie einen Wert** ein Geräte-Tag ein.
7. Wenn Sie weitere Gerätekategorien hinzufügen möchten, wählen Sie **Weitere hinzufügen** aus, und wiederholen Sie Schritt 6 für jede Kategorie, die Sie hinzufügen möchten.
8. Wählen Sie über **nehmen** aus.

Nachdem Sie die Geräte in der Geräteliste gefiltert haben, können Sie wie gewohnt Aktionen ausführen. Beispielsweise können Sie Sie auswählen und dann Konfigurationen zuweisen, deren Einstellungen bearbeiten (wenn es sich um Teams-Geräte handelt) usw. Wenn Sie fertig sind, können Sie den Filter entfernen, indem Sie das **X** neben dem **Tag** -Filtereintrag auswählen oder auf der rechten Seite der Liste **Alle löschen** auswählen.
