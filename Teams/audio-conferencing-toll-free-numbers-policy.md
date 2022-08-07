---
title: Richtlinien für gebührenfreie Audiokonferenznummern
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Erfahren Sie, wie Sie mit Audiokonferenzen in Microsoft 365 oder Office 365 von ihrem Telefon aus Besprechungen beitreten können.
ms.openlocfilehash: 7073fa9c870fc718b2d2c6e24e109878e0dd2d34
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269930"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>Richtlinieneinstellungen für Audiokonferenzen für gebührenpflichtige und gebührenfreie Nummern

## <a name="teams-audio-conferencing-policy"></a>Teams-Audiokonferenzrichtlinie

Verwenden Sie Audiokonferenzrichtlinien, um gebührenpflichtige und gebührenfreie Audiokonferenznummern zu verwalten, die in Besprechungseinladungen angezeigt werden, die von Benutzern in Ihrer Organisation erstellt wurden. Sie können eine der beiden automatisch erstellten Richtlinien verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Die beiden automatisch erstellten Richtlinien sind global (organisationsweiter Standard) und AllowTollFreeDialinFalse (allen vorhandenen Benutzern innerhalb der Organisation zugewiesen, die nicht für gebührenfreie Einwahlnummern aktiviert sind). Sie verwalten Audiokonferenzrichtlinien im Microsoft Teams Admin Center oder mithilfe von [PowerShell](teams-powershell-overview.md).

- Die Einstellung für AllowTollFreeDialin kann nicht mehr für einen einzelnen Benutzer über das Teams Admin Center oder PowerShell verwaltet werden. Mandantenadministratoren können diese Einstellung nur über die neue Audiokonferenzrichtlinie verwalten.
- Die globale Richtlinie kann im Teams Admin Center nicht geändert werden.

Wenn eine Teams-Audiokonferenzrichtlinie im Mandanten aktiviert ist, sind zwei automatisch erstellte Richtlinien im Mandanten verfügbar. Die beiden automatisch erstellten Richtlinien und ihre Standardeinstellungen sind:

### <a name="global-org-wide-default"></a>Global (organisationsweite Standardeinstellung)

In dieser Richtlinie wird der Wert für **AllowTollfreedialin** auf "EIN" festgelegt, und es werden keine Telefonnummern in der Richtlinie definiert. Dies ist die Standardrichtlinie für alle Benutzer im Mandanten, die zum Zeitpunkt des Starts **AllowTollfreedialin** auf **"Ein**" festgelegt haben.
Da für die Richtlinie keine Telefonnummern definiert sind, sind die in der Besprechung verfügbaren Telefonnummern, wenn Benutzer dieser Richtlinie eine Teams-Besprechung erstellen, dieselben Telefonnummern wie vor der Richtlinie. Diese Telefonnummern werden normalerweise standardmäßig auf das Land/den Standort des Benutzers festgelegt, es sei denn, sie werden vom Mandantenadministrator für einzelne Benutzer geändert.

Wenn beispielsweise einem Benutzer mit Sitz in Deutschland vor dem Start der Richtlinie für Audiokonferenzen gebührenpflichtige und gebührenfreie deutsche Telefonnummern zugewiesen wurden, wird dem Benutzer beim Start die globale Richtlinie zugewiesen, und die Telefonnummern, die er in seiner Besprechungseinladung weiterhin sehen wird, sind identisch mit der vor der Anwendung der Richtlinie (d. a.  die deutschen gebührenpflichtigen und gebührenfreien Nummern). Einem Endbenutzer wird beim Starten der Richtlinie keine Änderung angezeigt. Wenn jedoch ein Mandantenadministrator die globale Richtlinie ändert und bestimmte Telefonnummern in die Richtlinie einschließt, die sich von zuvor unterscheiden, werden allen Benutzern der Richtlinie nur die Telefonnummern angezeigt, die in der Richtlinie in geplanten Besprechungen enthalten sind.

> [!NOTE]
> Wenn ein Mandantenadministrator anstelle der Globalen Richtlinie eine benutzerdefinierte Richtlinie erstellt und auf Benutzer anwendet, werden die in der benutzerdefinierten Richtlinie definierten Einstellungen den Endbenutzern in ihren Besprechungseinladungen angezeigt.

Wenn die benutzerdefinierte Richtlinie z. B. "AllowTollFreeDialinFalse" aufweist und keine Telefonnummern definiert sind, können Benutzer dieser Richtlinie keine gebührenfreien Nummern haben, und da in der Richtlinie keine Telefonnummern definiert sind, wird die gebührenpflichtige Telefonnummer, die in von diesen Benutzern erstellten Besprechungseinladungen verwendet wird, dieselben Telefonnummern sein, die die Benutzer vor der Richtlinie hatten. Diese Telefonnummern werden normalerweise standardmäßig auf das Land/den Standort des Benutzers festgelegt, es sei denn, sie werden vom Mandantenadministrator für einzelne Benutzer geändert.

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

In dieser Richtlinie wird der Wert für **AllowTollfreedialin** auf **"Aus** " festgelegt, und es werden keine Telefonnummern in der Richtlinie definiert. Dies ist die Standardrichtlinie für alle Benutzer im Mandanten, die zum Zeitpunkt des Starts **AllowTollfreedialin** auf **"Aus**" festgelegt haben.

Da für die Richtlinie keine Telefonnummern definiert sind, sind die Telefonnummern, die in der Besprechung verfügbar sind, dieselben Telefonnummern, die die Benutzer vor der Richtlinie hatten, wenn Benutzer dieser Richtlinie eine Teambesprechung erstellen. Diese Telefonnummern sind normalerweise standardmäßig das Land, die Region oder der Standort des Benutzers, es sei denn, dies wurde vom Mandantenadministrator für einzelne Benutzer geändert.

Wenn z. B. einem Benutzer mit Sitz in Deutschland vor dem Start einer Audiokonferenzrichtlinie eine gebührenpflichtige deutsche Telefonnummer zugewiesen wurde, wird dem Benutzer beim Start die Richtlinie "AllowTollfreedialinFalse" zugewiesen, und die Telefonnummern, die er in seiner Besprechungseinladung weiterhin sehen wird, sind die gleichen wie zuvor (d. a. die gebührenpflichtige Deutschlandnummer). Einem Endbenutzer wird beim Starten der Richtlinie keine Änderung angezeigt. Wenn jedoch ein Mandantenadministrator die **AllowTollfreedialinFalse-Richtlinie** ändert und bestimmte Telefonnummern in die Richtlinie einbezieht, werden allen Richtlinienbenutzern nur die telefonnummern angezeigt, die in der Richtlinie in geplanten Besprechungen enthalten sind.

## <a name="create-a-custom-audio-conferencing-policy"></a>Erstellen einer benutzerdefinierten Audiokonferenzrichtlinie

Eine Übersicht über die Schritte:

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu "Besprechungen > Audiokonferenzen".
1. Klicken Sie auf Hinzufügen.
1. Geben Sie den Namen und die Beschreibung der Richtlinie ein. Der Name darf keine Sonderzeichen enthalten und maximal 64 Zeichen lang sein.
1. Wählen Sie die gewünschten Einstellungen aus.
1. Klicken Sie auf Speichern.

Sie können z. B. eine Gruppe von Benutzern haben, die regelmäßig Besprechungen mit Teilnehmern aus mehreren Ländern führen. In unserem Beispiel stammen die Teilnehmer aus Kanada, Botswana und Singapur, und sie alle möchten per Audiokonferenz an der Besprechung teilnehmen, indem sie eine Telefonnummer wählen. Sie können eine neue benutzerdefinierte Richtlinie namens "Kanada Botswana Singapur" erstellen und Telefonnummern aus diesen drei Ländern auswählen, die über die Option " **Telefonnummer hinzufügen** " in die Richtlinie aufgenommen werden sollen, und diese Richtlinie speichern. Sie können diese Richtlinie dann den erforderlichen Benutzern zuweisen.

Dadurch wird sichergestellt, dass Telefonnummern, die Sie für Kanada, Botsuana und Singapur ausgewählt haben, in die Besprechungseinladungen einbezogen werden, die von Benutzern dieser Richtlinie erstellt wurden.

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>Schrittweise Anleitungen zum Erstellen einer benutzerdefinierten Richtlinie basierend auf dem Beispiel

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Audiokonferenzen** für **Besprechungen** > .
2. Klicken Sie auf **Hinzufügen**.
3. Geben Sie den Namen und die Beschreibung der Richtlinie ein. Der Name darf keine Sonderzeichen enthalten und maximal 64 Zeichen lang sein.
4. Wählen Sie aus, ob gebührenfreie Nummern in Besprechungen einbezogen werden sollen, die von Benutzern dieser Richtlinie erstellt wurden. Wenn Sie dies auf **"Ein** " festlegen, können Sie gebührenfreie Telefonnummern in dieser Richtlinie hinzufügen.
5. Wählen Sie "Telefonnummer hinzufügen" aus.
6. Rechts auf dem Bildschirm wird ein Bereich geöffnet, der das Feld **"Nach Speicherort suchen** " enthält.
7. Geben Sie Kanada ein, und wählen Sie in den Ergebnissen eine Telefonnummer aus Kanada aus.
8. Klicken Sie auf **Hinzufügen**.
9. Wiederholen Sie die Schritte 6 und 7 auf die gleiche Weise, um Telefonnummern aus Botswana und Singapur zu durchsuchen und hinzuzufügen.
10. Wählen Sie gebührenfreie Nummern aus, wenn Sie die Einstellung " **Gebührenfreie Nummern in Besprechungen einschließen" aktiviert haben, die von Benutzern dieser Richtlinie** in Schritt 4 erstellt wurden.
11. Wählen Sie in der unteren rechten Ecke des Bereichs " **Hinzufügen** " aus. Die Telefonnummern aus den drei von Ihnen ausgewählten Ländern werden aufgelistet.
12. Es gibt eine Rangspalte, die die Reihenfolge bestimmt, in der die Telefonnummern in Besprechungseinladungen angezeigt werden, die von Benutzern dieser Richtlinie erstellt wurden. Sie können die Reihenfolge ändern, indem Sie eine Telefonnummer auswählen und mithilfe der Schaltflächen " **Nach oben** " bzw. " **Nach unten"** nach oben oder unten verschieben.
13. Nachdem Sie die Telefonnummern in der Reihenfolge Ihrer Einstellung festgelegt haben, wählen Sie **"Speichern"** aus.
14. Ihre benutzerdefinierte Richtlinie mit dem Namen "Kanada Botswana Singapur" wird erstellt.
15. Nach Abschluss der Erstellung können Sie diese Richtlinie Ihren Benutzern zuweisen.

## <a name="edit-a-meeting-policy"></a>Bearbeiten einer Besprechungsrichtlinie

Sie können alle benutzerdefinierten Richtlinien bearbeiten, die Sie erstellen. (Beachten Sie, dass die globale Richtlinie nicht im Teams Admin Center bearbeitet werden kann.)

1. Navigieren Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Audiokonferenzen** für **Besprechungen** > .
1. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten, indem Sie links neben dem Richtliniennamen und dann auf **"Bearbeiten"** klicken.
1. Änderungen vornehmen.
1. Klicken Sie auf **Speichern**.

> [!NOTE]
> Sie können eine Richtlinie nicht löschen, solange Sie Benutzern zugewiesen ist. Sie müssen allen betroffenen Benutzern eine andere Richtlinie zuweisen, und dann können Sie die ursprüngliche Richtlinie löschen.

## <a name="assign-a-meeting-policy-to-users"></a>Benutzern eine Besprechungsrichtlinie zuweisen

> [!IMPORTANT]
> Sobald eine neue Audiokonferenzrichtlinie auf einen Benutzer angewendet wurde, sind die in der Richtlinie definierten Telefonnummern nur in neuen Besprechungen verfügbar, die vom Benutzer mit dieser Richtlinie erstellt wurden. Alle alten und wiederkehrenden Besprechungen, die vor der Richtlinie geplant wurden, zeigen weiterhin die alten Einstellungen an, z. B. eine gebührenpflichtige und eine gebührenfreie Nummer (wenn für diesen Benutzer gebührenfrei aktiviert wurde). Ein Szenario hier könnte sein, dass ein Benutzer " **Gebührenfreies Zulassen** " aktiviert und eine gebührenfreie Nummer zugewiesen hatte und Besprechungsserien für die Zukunft erstellt hat. Wenn Sie in diesem Szenario eine benutzerdefinierte Richtlinie mit **deaktivierter** Option "AllowTollfreeDialIn" erstellen und auf diesen Benutzer anwenden, enthalten alle neuen Besprechungen, die von diesem Benutzer erstellt wurden, keine gebührenfreien Nummern, aber die alten und wiederkehrenden Besprechungen zeigen weiterhin gebührenfreie Nummern an. Wenn Anrufer also diese gebührenfreie Nummer wählen, um an der Besprechung teilzunehmen, schlägt der Anruf fehl, da der Gebührenfreie Anruf für diesen Benutzer aufgrund der Richtlinie jetzt deaktiviert ist. Um dies zu verhindern, können Sie die alten Besprechungen der Benutzer migrieren, nachdem Sie ihnen die neue Audiokonferenzrichtlinie zugewiesen haben. Überprüfen Sie [die Verwendung des Besprechungsmigrationsdiensts (MEETING Migration Service, MMS).](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

Sie können eine Richtlinie direkt Benutzern oder einer Gruppe zuweisen, deren Mitglieder die Benutzer sind (sofern für den Richtlinientyp unterstützt), entweder einzeln oder in größeren Zahlen über eine Batchzuweisung (sofern für den Richtlinientyp unterstützt).

Informationen zu den verschiedenen Möglichkeiten, wie Sie Benutzern Richtlinien zuweisen können, finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md).

> [!NOTE]
> Einem Benutzer kann jeweils nur eine Audiokonferenzrichtlinie zugewiesen werden.

> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die zugewiesenen Telefonnummern in Ihrer Besprechungseinladung angezeigt werden. Wenn aktualisierte Nummern nicht angezeigt werden, warten Sie mindestens 24 Stunden, bevor Sie sich an den Support wenden.

### <a name="known-issue"></a>Bekanntes Problem

Wenn Sie eine Besprechung mithilfe der Option "**Jetzt besprechen"** von Microsoft Teams > Kalender > Besprechungsmenü starten, wählen Sie die Auslassungspunkte aus ... und dann "Besprechungsinformationen" gibt es ein Problem mit dem unteren Teil des Abschnitts unter **"Oder anrufen in" (nur Audio).** Alle in der Richtlinie definierten Telefonnummern werden angezeigt, aber die Ausrichtung der Nummern macht es schwierig zu lesen.
