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
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
description: Erfahren Sie, wie Sie Tags auf Ihren Microsoft Teams-Geräten verwalten und filtern.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a372aacb7a8917dc169855fd671b1382d390f32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271350"
---
# <a name="manage-microsoft-teams-device-tags"></a>Verwalten von Microsoft Teams-Gerätetags

Mithilfe von Gerätetags in Microsoft Teams können Sie die Geräte, die Sie in Ihrer Organisation bereitgestellt haben, gruppieren, organisieren und einfacher verwalten. Mit dem Microsoft Teams Admin Center können Sie ein oder mehrere Tags zu Geräten hinzufügen, Filter verwenden, um Geräte anzuzeigen, die dem von Ihnen angegebenen Tag entsprechen, und dann Aktionen auf den Geräten ausführen, die über dieses Tag verfügen.

Sie können mehr als einem Gerätetyp ein Gerätetag hinzufügen. Wenn Sie jedoch einen Gerätebereich im Admin Center öffnen, werden nur die Geräte dieses Typs zurückgegeben. Beispielsweise können Sie das "Corporate"-Tag sowohl Smartphones als auch Teams-Räume Geräten zuweisen. Wenn Sie in **Teams-Gerätetelefonen** >  nach dem "Corporate"-Tag suchen, werden nur Telefone zurückgegeben. Wenn Sie in **Teams-Geräten** >  nach dem Tag "Unternehmen" suchen **Teams-Räume** werden ebenfalls nur Teams-Räume Geräte zurückgegeben.

Zum Verwalten von Gerätetags müssen Sie ein globaler Administrator, Teams-Dienstadministrator oder Teams-Geräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden von Microsoft Teams-Administratorrollen zum Verwalten von Teams](../using-admin-roles.md).

> [!IMPORTANT]
> Gerätetags werden dem Ressourcenkonto zugewiesen, das bei einem Gerät angemeldet ist. Wenn Sie ein Ressourcenkonto von einem Gerät abmelden und es dann verwenden, um sich bei einem anderen Gerät anzumelden, werden die Gerätetags auf das neue Gerät angewendet.

## <a name="create-remove-or-rename-device-tags"></a>Erstellen, Entfernen oder Umbenennen von Gerätetags

Mithilfe des Bereichs "Gerätetagverwaltung" können Sie Folgendes ausführen:

- Alle Gerätetags anzeigen.
- Erstellen Sie auf einfache Weise mehrere Gerätetags, und weisen Sie sie später Geräten zu. Tags können bis zu 25 Zeichen lang sein.
- Entfernen Sie Gerätetags, die nicht mehr benötigt werden. Bevor Sie ein Gerätetag entfernen können, müssen Sie es von allen Geräten entfernen, zu dem es hinzugefügt wurde.
- Umbenennen von Gerätetags. Wenn Sie ein Gerätetag umbenennen, wird diese Änderung auf allen Geräten, denen sie hinzugefügt wurde, widergespiegelt. Tags können bis zu 25 Zeichen lang sein.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **Teams-Geräten** , und wählen Sie dann einen beliebigen Gerätebereich aus, z. B. **Telefone**.
3. Wählen Sie " **Aktionen"** in der oberen rechten Ecke der Seite und dann **"Alle Gerätetags" aus**.
4. Um ein Gerätetag zu erstellen, wählen Sie **+Hinzufügen** aus, geben Sie einen Wert für das Gerätetag an, und wählen Sie das Symbol **"Speichern** " aus.
5. Um ein Gerätetag zu entfernen, wählen Sie die Auslassungspunkte **...** neben dem Gerätetag aus, das Sie entfernen möchten, und wählen Sie **"Löschen"** aus.
    > [!NOTE]
    > Wenn Sie versuchen, ein Gerätetag zu entfernen, das zu Geräten hinzugefügt wurde, erhalten Sie eine Meldung, in der Sie gefragt werden, ob Sie es von allen Geräten entfernen möchten. Wenn Sie dies tun möchten und das Gerätetag weiterhin entfernen möchten, wählen Sie " **Geräte markieren" aus**.
6. Um ein Gerätetag umzubenennen, wählen Sie die Auslassungspunkte **...** neben dem Gerätetag aus, das Sie umbenennen möchten, und wählen Sie **"Bearbeiten"** aus. Geben Sie einen neuen Wert für das Gerätetag an, und wählen Sie das Symbol **"Speichern** " aus.

## <a name="add-or-remove-tags-on-a-single-device"></a>Hinzufügen oder Entfernen von Tags auf einem einzelnen Gerät

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen lang sein.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **Teams-Geräten** , und wählen Sie dann den Gerätebereich aus, der das Gerät enthält, auf dem Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben dem Gerät, auf dem Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **"Kategorien verwalten"** aus.
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagnamens, den Sie hinzufügen möchten.
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **"\<tag name>" als neues Tag hinzufügen** aus. Tags können bis zu 25 Zeichen lang sein.
5. Wenn Sie ein Tag entfernen möchten, wählen Sie **neben** dem Tag, das Sie entfernen möchten, X aus.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Tags hinzufügen oder entfernen möchten.
7. Wählen Sie **"Übernehmen" aus**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Hinzufügen oder Entfernen von Tags auf mehreren Geräten

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen lang sein. Wenn Sie ein Tag von mehreren Geräten entfernen möchten, müssen Sie den Teams-Benutzer auswählen, der dem Gerät zugeordnet ist, und das Tag aus dem Benutzer entfernen.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **Teams-Geräten** , und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, auf denen Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben den Geräten, auf dem Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **"Kategorien verwalten"** aus.
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagsnamens, den Sie in **"Kategorien verwalten" für alle Geräte von Teams-Benutzern** hinzufügen möchten.
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen Sie **"\<tag name>" als neues Tag hinzufügen** aus.
5. Wenn Sie ein Tag entfernen möchten:
    1. Erweitern **Sie "Teams-Benutzer auswählen"**.
    2. Erweitern Sie **\<x> Tags** unter dem Namen des Teams-Benutzers, aus dem Sie Tags entfernen möchten.
    3. Wählen Sie **"X** " neben dem Tag aus, das Sie entfernen möchten.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Tags hinzufügen oder entfernen möchten.
7. Wählen Sie **"Übernehmen" aus**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Verwenden von Filtern zum Zurückgeben von Geräten mit einem bestimmten Tag

Wenn Sie Ihren Geräten Gerätetags hinzugefügt haben, können Sie diese verwenden, um die Geräteliste so zu filtern, dass nur die Geräte zurückgegeben werden, denen ein bestimmtes Tag hinzugefügt wurde. Dies kann hilfreich sein, wenn Sie nur alle Geräte in einem bestimmten Raum, alle Geräte eines bestimmten Typs oder andere Kriterien anzeigen möchten, die Sie beim Hinzufügen Ihrer Tags verwendet haben. Sie können auch Massenaktionen auf zurückgegebenen Geräten ausführen, z. B. Updates in Wellen anwenden oder unterschiedliche Konfigurationsrichtlinien festlegen, je nachdem, welche Gruppen von Geräten mithilfe von Gerätetags identifiziert wurden.

1. Melden Sie sich beim Microsoft Teams Admin Center an, indem Sie den Besuch besuchen https://admin.teams.microsoft.com.
2. Navigieren Sie zu **Teams-Geräten** , und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, die Sie filtern möchten.
3. Wählen Sie das **Filtersymbol** aus.
4. Wenn Sie nur ein einzelnes Tag angeben möchten, oder wenn Sie Geräte mit allen von Ihnen angegebenen Tags suchen möchten, wählen Sie **"Alle diese Bedingungen erfüllen" aus**.
5. Wenn Sie Geräte suchen möchten, die einem oder mehreren Gerätetags entsprechen, wählen Sie " **Mit einer dieser Bedingungen übereinstimmen" aus**.
6. Wählen Sie das **Tag-Feld** aus, und geben Sie dann einen Gerätetagnamen im Feld **"Wert eingeben" an** .
7. Wenn Sie weitere Gerätetags hinzufügen möchten, wählen Sie **"Weitere hinzufügen"** aus, und wiederholen Sie Schritt 6 für jedes Tag, das Sie hinzufügen möchten.
8. Wählen Sie **"Übernehmen" aus**.

Nachdem Sie die Geräte in Ihrer Geräteliste gefiltert haben, können Sie aktionen auf ihnen wie gewohnt ausführen. Sie können sie beispielsweise auswählen und dann Konfigurationen zuweisen, ihre Einstellungen bearbeiten (wenn sie Teams-Räume Geräten sind) usw. Wenn Sie fertig sind, können Sie den Filter entfernen, indem Sie das **X**  neben dem **Tagfiltereintrag** auswählen oder auf der rechten Seite der Liste **"Alle** löschen" auswählen.
