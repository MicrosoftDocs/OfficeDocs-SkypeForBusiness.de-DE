---
title: Nicht zugewiesene Telefonnummer Erstellen neuer oder Bearbeiten vorhandener Telefonnummern
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.
ms.openlocfilehash: 9cef4ae8075bf4982ab9c3ddd857062d4fa1a824
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711732"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Nicht zugewiesene Telefonnummer: Erstellen einer neuen oder Bearbeiten einer vorhandenen nicht zugewiesenen Nummer

> [!NOTE]
> Exchange UM bleibt in Skype for Business Server 2019 verfügbar, wenn Sie Skype for Business 2019 in Exchange 2013 oder Exchange 2016 integrieren. Aufgrund von Änderungen bei der Unterstützung in Exchange 2019 wird die Exchange UM-Integration zugunsten von Cloud Voicemail- und Cloud-automatische Telefonzentrale hervorgehoben.

Nicht zugewiesene Nummern sind Rufnummern, die für Ihre Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. In der Tabelle mit den nicht zugewiesenen Nummern ist angegeben, wie Anrufe bei nicht zugewiesenen Nummern behandelt werden sollen.

> [!IMPORTANT]
> Klicken Sie nach Abschluss der Erstellung eines neuen Bereichs nicht zugewiesener Nummern bzw. der Bearbeitung eines vorhandenen Bereichs auf **OK**, um zur Seite **Nicht zugewiesene Nummer** zurückzukehren, auf der alle Nummernbereiche aufgeführt sind. Die Änderungen, die Sie auf der Seite **Neuer Bereich nicht zugewiesener Nummern** oder der Seite **Bereich nicht zugewiesener Nummern bearbeiten** vorgenommen haben, werden erst in die Datenbank übernommen, wenn Sie auf der Seite **Nicht zugewiesene Nummer** auf **Commit für alle Elemente ausführen** klicken.

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In der folgenden Liste sind die Felder der Seite beschrieben.

- **Name** Geben Sie einen beschreibenden Namen ein, der den Bereich nicht zugewiesener Nummern identifiziert. Nach dem Speichern des Bereichs kann dieser Name nicht mehr geändert werden.

- **Nummernbereich** Geben Sie im ersten Feld die Anfangsnummer des Bereichs nicht zugewiesener Nummern ein. Geben Sie im zweiten Feld die Endnummer des Bereichs ein.

  - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.

  - Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen, und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.

  - Die Zahl muss mit dem regulären Ausdruck ( `tel:` )?( \+ )? übereinstimmen. [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. Dies bedeutet, dass die Zahl mit der Zeichenfolge "tel:" beginnen kann. Wenn Sie diese Zeichenfolge nicht angeben, wird sie automatisch für Sie hinzugefügt, z. B. ein Pluszeichen (+) und eine Ziffer 1 bis 9. Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.

- **Ansagedienst** Wählen **Sie Ansage** aus, damit die Ansageanwendung den eingehenden Anruf verarbeiten soll, oder **Exchange UM,** damit ein Exchange UM-automatische Telefonzentrale den eingehenden Anruf verarbeiten kann.

- Bei Auswahl von **Ankündigung** unter **Ankündigungsdienst**:

  - **FQDN des Zielservers** Wählen Sie die Dienst-ID des Anwendungsdiensts aus, der die Ansageanwendung ausgeführt hat, die eingehende Anrufe an diesen Bereich nicht zugewiesener Nummern verarbeiten soll.

  - **Ankündigung** Wählen Sie die Ansage aus, die für diesen Bereich nicht zugewiesener Nummern abgespielt werden soll.

- Bei Auswahl von **Exchange UM** unter **Ankündigungsdienst**:

  - **automatische Telefonzentrale Telefonnummer** Wählen Sie die Telefonnummer für die Exchange UM-automatische Telefonzentrale.

Ausführliche Informationen zu Ankündigungsfeatures und -funktionen finden Sie unter [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Bereichen nicht zugewiesener Nummern finden Sie unter [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in der Betriebsdokumentation.


