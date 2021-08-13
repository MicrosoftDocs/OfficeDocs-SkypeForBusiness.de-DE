---
title: Verwalten und Filtern Microsoft Teams Gerätetags
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
description: Erfahren Sie, wie Sie Tags auf Ihren Mobilen Geräten Microsoft Teams filtern.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a264b6f2679576fac0eb95dbbfafa93037b98cfc3b5f5dfbfa9a07d6b6eeb3bc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321487"
---
# <a name="manage-microsoft-teams-device-tags"></a>Verwalten Microsoft Teams von Gerätetags

Gerätetags in Microsoft Teams ihnen das Gruppieren, Organisieren und einfachere Verwalten der Geräte ermöglichen, die Sie in Ihrer Organisation bereitgestellt haben. Im Microsoft Teams Admin Center können Sie Geräte einen oder mehrere Tags hinzufügen, Filter verwenden, um Geräte anzeigen, die dem von Ihnen angegebenen Tag entsprechen, und dann Aktionen auf den Geräten ausführen, die dieses Tag enthalten.

Sie können ein Gerätetag zu mehreren Gerätetypen hinzufügen. Wenn Sie jedoch einen Gerätebereich im Admin Center öffnen, werden nur die Geräte dieses Typs zurückgegeben. Beispielsweise können Sie das Tag "Unternehmens" sowohl Telefonen als auch Teams-Räume zuweisen. Wenn Sie in Gerätetelefone nach dem Tag "Corporate"  >  suchen, werden nur Telefone zurückgegeben. Ebenso werden bei der Suche nach dem Tag "Unternehmens" **in** Geräte Teams-Räume nur Teams-Räume-Geräte  >  zurückgegeben.

Zum Verwalten von Gerätetags müssen Sie ein globaler Administrator, Teams Dienstadministrator oder Teams Geräteadministrator sein. Weitere Informationen zu Administratorrollen finden Sie unter Verwenden [Microsoft Teams zum Verwalten von Teams.](../using-admin-roles.md)

> [!IMPORTANT]
> Gerätetags werden dem Ressourcenkonto zugewiesen, das bei einem Gerät angemeldet ist. Wenn Sie ein Ressourcenkonto von einem Gerät abmelden und es dann für die Anmeldung bei einem anderen Gerät verwenden, werden die Gerätetags auf das neue Gerät angewendet.

## <a name="create-remove-or-rename-device-tags"></a>Erstellen, Entfernen oder Umbenennen von Gerätetags

Mithilfe des Gerätetag-Verwaltungsbereichs können Sie:

- Alle Gerätetags sehen.
- Erstellen Sie auf einfache Weise mehrere Gerätetags, und weisen Sie sie geräten zu einem späteren Zeitpunkt zu. Tags können bis zu 25 Zeichen lang sein.
- Entfernen Sie gerätetags, die nicht mehr benötigt werden. Bevor Sie ein Gerätetag entfernen können, müssen Sie es von allen Geräten entfernen, auf die es hinzugefügt wurde.
- Benennen Sie Gerätetags um. Wenn Sie ein Gerätetag umbenennen, wird diese Änderung auf allen Geräten widerzuspiegeln, denen es hinzugefügt wurde. Tags können bis zu 25 Zeichen lang sein.

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann einen beliebigen Gerätebereich aus, z. B. **Telefone.**
3. Wählen **Sie** in der oberen rechten Ecke der Seite Aktionen und dann **Alle Gerätetags aus.**
4. Um ein Gerätetag zu erstellen, wählen Sie **+ Hinzufügen** aus, geben Sie einen Wert für das Gerätetag an, und wählen Sie das **Symbol Speichern** aus.
5. Um ein Gerätetag zu entfernen, wählen Sie die Auslassungspunkte **(...)** neben dem Gerätetag, das Sie entfernen möchten, und dann Löschen **aus.**
    > [!NOTE]
    > Wenn Sie versuchen, ein Gerätetag zu entfernen, das Geräten hinzugefügt wurde, erhalten Sie eine Meldung, in der Sie gefragt werden, ob Sie es von allen Geräten entfernen möchten. Wenn Sie dies tun und mit dem Entfernen des Gerätetags fortfahren möchten, wählen Sie **Gerätetag entfernen aus.**
6. Um ein Gerätetag umzubenennen, wählen Sie die Auslassungspunkte **(...)** neben dem Gerätetag, das Sie umbenennen möchten, und dann **Bearbeiten aus.** Geben Sie einen neuen Wert für das Gerätetag ein, und wählen Sie das **Symbol Speichern** aus.

## <a name="add-or-remove-tags-on-a-single-device"></a>Hinzufügen oder Entfernen von Tags auf einem einzelnen Gerät

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen lang sein.

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der das Gerät enthält, auf dem Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben das Gerät, dem Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **Dann Kategorien verwalten aus.**
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagsnamens, den Sie hinzufügen möchten.
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen **Sie Als neues Tag hinzufügen " \<tag name> aus.** Tags können bis zu 25 Zeichen lang sein.
5. Wenn Sie ein Tag entfernen möchten, wählen Sie neben dem Tag, das Sie entfernen möchten, **das** X aus.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Kategorien hinzufügen oder entfernen möchten.
7. Wählen Sie **Übernehmen aus.**

## <a name="add-or-remove-tags-on-multiple-devices"></a>Hinzufügen oder Entfernen von Tags auf mehreren Geräten

Wenn Sie einem Gerät Tags hinzufügen, können Sie entweder ein vorhandenes Tag auswählen oder ein neues Tag erstellen. Tags können bis zu 25 Zeichen lang sein. Wenn Sie ein Tag von mehreren Geräten entfernen möchten, müssen Sie den Teams-Benutzer auswählen, der dem Gerät zugeordnet ist, und das Tag vom Benutzer entfernen.

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der die Geräte enthält, auf die Sie Tags hinzufügen oder entfernen möchten.
3. Setzen Sie ein Häkchen neben die Geräte, auf die Sie Tags hinzufügen oder entfernen möchten, und wählen Sie **Tags verwalten aus.**
4. Wenn Sie ein Tag hinzufügen möchten:
    1. Beginnen Sie mit der Eingabe des Tagsnamens, den Sie hinzufügen möchten, in Verwalten von Tags für alle Geräte **Teams Benutzer.**
    2. Wenn das Tag bereits vorhanden ist, wählen Sie es aus der Liste der zurückgegebenen Tags aus.
    3. Wenn das Tag nicht vorhanden ist, wählen **Sie Als neues Tag hinzufügen " \<tag name> aus.**
5. Wenn Sie ein Tag entfernen möchten:
    1. Erweitern **Sie Teams Benutzer auswählen**.
    2. Erweitern **\<x> Sie** Tags unter dem Namen des Teams, aus dem Sie Kategorien entfernen möchten.
    3. Wählen **Sie neben** dem Tag, das Sie entfernen möchten, das X aus.
6. Wiederholen Sie die vorstehenden Schritte, wenn Sie weitere Kategorien hinzufügen oder entfernen möchten.
7. Wählen Sie **Übernehmen aus.**

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Verwenden von Filtern zum Zurückgeben von Geräten mit einem bestimmten Tag

Wenn Sie Ihren Geräten Gerätetags hinzugefügt haben, können Sie diese verwenden, um die Geräteliste zu filtern, um nur Geräte zurückzukehren, für die ein angegebenes Tag hinzugefügt wurde. Dies kann hilfreich sein, wenn Sie nur alle Geräte in einem bestimmten Raum, alle Geräte eines bestimmten Typs oder andere Kriterien anzeigen möchten, die Sie beim Hinzufügen Ihrer Tags verwendet haben. Sie können auch Massenaktionen für zurückgegebene Geräte ausführen, z. B. Updates in Wellen anwenden oder je nach Gerätegruppen, die mit Gerätetags identifiziert werden, unterschiedliche Konfigurationsrichtlinien festlegen.

1. Melden Sie sich bei Microsoft Teams Admin Center an, indem Sie https://admin.teams.microsoft.com besuchen.
2. Navigieren Sie **zu Geräte,** und wählen Sie dann den Gerätebereich aus, der die zu filternde Geräte enthält.
3. Wählen Sie das **Symbol Filter** aus.
4. Wenn Sie nur ein einzelnes Tag angeben oder nach Geräten suchen möchten, die alle von Ihnen angegebenen Tags enthalten, wählen Sie Alle **diese Bedingungen erfüllen aus.**
5. Wenn Sie nach Geräten suchen möchten, die einem oder mehreren Gerätetags entsprechen, wählen **Sie Übereinstimmung mit einer der folgenden Bedingungen aus.**
6. Wählen Sie **das Feld Tag** aus, und geben Sie dann im Feld Wert eingeben einen **Gerätetagnamen** an.
7. Wenn Sie weitere Gerätetags hinzufügen möchten, wählen Sie **Weitere** hinzufügen aus, und wiederholen Sie Schritt 6 für jedes hinzuzufügende Tag.
8. Wählen Sie **Übernehmen aus.**

Nachdem Sie die Geräte in der Geräteliste gefiltert haben, können Sie wie gewohnt Aktionen an den Geräten ausführen. Sie können sie z. B. auswählen und dann Konfigurationen zuweisen, deren Einstellungen bearbeiten (wenn sie Teams-Räume sind) und so weiter. Wenn Sie fertig sind, können Sie den Filter entfernen, indem Sie  **das X** neben dem **Filtereintrag Tag** auswählen oder auf der rechten Seite der Liste Alle löschen auswählen.
