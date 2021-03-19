---
title: Verwalten und Filtern von Microsoft Teams-Gerätetags
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
description: Erfahren Sie, wie Sie Tags auf Ihren Microsoft Teams-Geräten verwalten und filtern.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4f8ac718a965834678098a8960347278d13aa3
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874995"
---
# <a name="manage-microsoft-teams-device-tags"></a>Verwalten von Microsoft Teams-Gerätetags

Mit Gerätetags in Microsoft Teams können Sie die Geräte, die Sie in Ihrer Organisation bereitgestellt haben, gruppieren, organisieren und einfacher verwalten. Mit dem Microsoft Teams Admin Center können Sie Geräte ein oder mehrere Tags hinzufügen, Mithilfe von Filtern Geräte anzeigen, die dem von Ihnen angegebenen Tag entsprechen, und dann Aktionen auf den Geräten ausführen, die über dieses Tag verfügen.

Sie können mehreren Gerätetypen ein Gerätetag hinzufügen. Wenn Sie jedoch einen Gerätebereich im Admin Center öffnen, werden nur die Geräte dieses Typs zurückgegeben. Sie können z. B. das Tag "Unternehmen" sowohl Smartphones als auch Teams Rooms-Geräten zuweisen. Wenn Sie unter Gerätetelefone nach dem Tag "Unternehmen"  >  suchen, werden nur Telefone zurückgegeben. Wenn Sie in "Devices Teams Rooms" nach dem Tag "Corporate" suchen, werden nur Teams  >  Rooms-Geräte zurückgegeben.

Zum Verwalten von Gerätetags müssen Sie globaler Administrator, Teamdienstadministrator oder Teamgeräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams.](../using-admin-roles.md)

> [!IMPORTANT]
> Gerätetags werden dem Ressourcenkonto zugewiesen, das bei einem Gerät angemeldet ist. Wenn Sie ein Ressourcenkonto von einem Gerät abmelden und es dann zum Anmelden bei einem anderen Gerät verwenden, werden die Gerätetags auf das neue Gerät angewendet.

## <a name="create-remove-or-rename-device-tags"></a>Erstellen, Entfernen oder Umbenennen von Gerätetags

Mithilfe des Gerätetagverwaltungspanels können Sie:

- Sehen Sie sich alle Gerätetags an.
- Erstellen Sie einfach mehrere Gerätetags, und weisen Sie sie geräten zu einem späteren Zeitpunkt zu. Tags können bis zu 25 Zeichen umfassen.
- Entfernen Sie Gerätetags, die nicht mehr benötigt werden. Bevor Sie ein Gerätetag entfernen können, müssen Sie es von allen Geräten entfernen, auf die es hinzugefügt wurde.
- Benennen Sie Gerätetags um. Wenn Sie ein Gerätetag umbenennen, wird diese Änderung auf allen Geräten wider, denen sie hinzugefügt wurde. Tags können bis zu 25 Zeichen umfassen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann einen beliebigen Gerätebereich aus, z. B. **Smartphones.**
3. Wählen **Sie** in der oberen rechten Ecke der Seite Aktionen und dann **Alle Gerätetags aus.**
4. Um ein Gerätetag zu erstellen, wählen Sie **+ Hinzufügen** aus, geben Sie einen Wert für das Gerätetag an, und wählen Sie das Symbol **Speichern** aus.
5. Um ein Gerätetag zu entfernen, wählen Sie die Auslassungspunkte **...** neben dem Gerätetag aus, das Sie entfernen möchten, und wählen Sie **Löschen aus.**
    > [!NOTE]
    > Wenn Sie versuchen, ein Gerätetag zu entfernen, das geräten hinzugefügt wurde, erhalten Sie eine Meldung, in der Sie gefragt werden, ob Sie es von allen Geräten entfernen möchten. Wenn Sie dies tun und das Gerätetag weiterhin entfernen möchten, wählen Sie **Gerätetag entfernen aus.**
6. Um ein Gerätetag umzubenennen, wählen Sie die Auslassungspunkte **...** neben dem Gerätetag aus, das Sie umbenennen möchten, und wählen Sie **Bearbeiten aus.** Geben Sie einen neuen Wert für das Gerätetag an, und wählen Sie das **Symbol Speichern** aus.

## <a name="add-or-remove-tags-on-a-single-device"></a>Hinzufügen oder Entfernen von Tags auf einem einzelnen Gerät

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen umfassen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der das Gerät enthält, auf dem Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben dem Gerät, auf dem Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **Tags verwalten aus.**
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagsnamens, den Sie hinzufügen möchten.
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **Hinzufügen " " als neues Tag \<tag name> aus.** Tags können bis zu 25 Zeichen umfassen.
5. Wenn Sie ein Tag entfernen möchten, wählen Sie **X** neben dem Tag aus, das Sie entfernen möchten.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Tags hinzufügen oder entfernen möchten.
7. Wählen Sie **Übernehmen aus.**

## <a name="add-or-remove-tags-on-multiple-devices"></a>Hinzufügen oder Entfernen von Tags auf mehreren Geräten

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen umfassen. Wenn Sie ein Tag von mehreren Geräten entfernen möchten, müssen Sie den Teams-Benutzer auswählen, der dem Gerät zugeordnet ist, und das -Tag aus dem Benutzer entfernen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, auf die Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben den Geräten, auf die Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **Tags verwalten aus.**
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagsnamens, den Sie hinzufügen möchten, in Verwalten von Tags **für alle Geräte von Teams-Benutzern.**
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **Hinzufügen " " als neues Tag \<tag name> aus.**
5. Wenn Sie ein Tag entfernen möchten:
    1. Erweitern **Wählen Sie Teams-Benutzer aus.**
    2. Erweitern **\<x> Sie Tags** unter dem Namen des Teams-Benutzers, aus dem Sie Tags entfernen möchten.
    3. Wählen **Sie X** neben dem Tag aus, das Sie entfernen möchten.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Tags hinzufügen oder entfernen möchten.
7. Wählen Sie **Übernehmen aus.**

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Verwenden von Filtern zum Zurückgeben von Geräten mit einem bestimmten Tag

Wenn Sie Ihren Geräten Gerätetags hinzugefügt haben, können Sie sie verwenden, um die Geräteliste zu filtern, um nur die Geräte zurückzukehren, auf die ein angegebenes Tag hinzugefügt wurde. Dies kann hilfreich sein, wenn Sie nur alle Geräte in einem bestimmten Raum, alle Geräte eines bestimmten Typs oder alle anderen Kriterien anzeigen möchten, die Sie beim Hinzufügen Ihrer Tags verwendet haben. Sie können auch Massenaktionen auf zurückgegebenen Geräten ausführen, z. B. Updates in Wellen anwenden oder je nach Gerätegruppen, die mithilfe von Gerätetags identifiziert werden, unterschiedliche Konfigurationsrichtlinien festlegen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie zu https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, die Sie filtern möchten.
3. Wählen Sie das **Symbol Filter** aus.
4. Wenn Sie nur ein einzelnes Tag angeben oder Geräte suchen möchten, die alle von Ihnen angegebenen Tags enthalten, wählen Sie Alle diese **Bedingungen vergleichen aus.**
5. Wenn Sie Geräte suchen möchten, die einem oder mehreren Gerätetags entsprechen, wählen Sie Übereinstimmen mit einer **dieser Bedingungen aus.**
6. Wählen Sie das **Feld Tag** aus, und geben Sie dann im Feld Wert eingeben einen **Gerätetagnamen** an.
7. Wenn Sie weitere Gerätetags hinzufügen  möchten, wählen Sie Weitere hinzufügen aus, und wiederholen Sie Schritt 6 für jedes Tag, das Sie hinzufügen möchten.
8. Wählen Sie **Übernehmen aus.**

Nachdem Sie die Geräte in Ihrer Geräteliste gefiltert haben, können Sie aktionen auf diesen Geräten wie gewohnt ausführen. Sie können sie z. B. auswählen und dann Konfigurationen zuweisen, deren Einstellungen bearbeiten (wenn es sich um Teams Rooms-Geräte gibt) und so weiter. Wenn Sie fertig sind, können Sie den Filter entfernen, indem Sie  das **X** neben dem **Filtereintrag Tag** auswählen oder ganz auf der rechten Seite der Liste löschen auswählen.
