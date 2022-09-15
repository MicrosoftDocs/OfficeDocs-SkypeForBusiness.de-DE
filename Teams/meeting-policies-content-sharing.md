---
title: Verwalten von Besprechungsrichtlinien für die Inhaltsfreigabe
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für die Inhaltsfreigabe verwalten.
ms.openlocfilehash: d3ae689ceb2c864f3f70da91728b8607aaa1e0e2
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706692"
---
# <a name="meeting-policy-settings---content-sharing"></a>Besprechungsrichtlinieneinstellungen – Inhaltsfreigabe

<a name="bkcontentsharing"> </a>

In diesem Artikel werden die folgenden Besprechungsrichtlinieneinstellungen im Zusammenhang mit der Inhaltsfreigabe beschrieben:

- [Bildschirmübertragungsmodus](#screen-sharing-mode)
- [Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert](#allow-a-participant-to-give-or-request-control)
- [Externe Teilnehmer können die Steuerung übergeben oder anfordern](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [Whiteboard](#whiteboard)
- [Freigegebene Notizen](#shared-notes)

## <a name="screen-sharing-mode"></a>Bildschirmfreigabemodus

Diese Einstellung ist eine Kombination aus organisatorspezifischen und benutzerspezifischen Richtlinien. Diese Einstellung steuert, ob die Desktop- und Fensterfreigabe in der Besprechung des Benutzers zulässig ist. Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. externe Teilnehmer), erben die Richtlinie des Besprechungsorganisators.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Gesamter Bildschirm**    | Die vollständige Desktop- und Anwendungsfreigabe ist in der Besprechung zulässig. |
|**Einzelne Anwendung**   | Die Anwendungsfreigabe ist in der Besprechung zulässig.        |
|**Deaktiviert**     |Die Bildschirm- und Anwendungsfreigabe ist in der Besprechung deaktiviert.       |

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie |Bildschirmübertragungsmodus |
|---------|---------|---------|
|Daniela  | Global   | Gesamter Bildschirm |
|Amala   | Location1MeetingPolicy  | Deaktiviert |

Besprechungen, die von Daniela gehostet werden, ermöglichen Besprechungsteilnehmern, den gesamten Bildschirm oder eine bestimmte Anwendung freizugeben. Wenn Amanda an Danielas Besprechung teilnimmt, kann Amanda ihren Bildschirm oder eine bestimmte Anwendung nicht teilen, da die Richtlinieneinstellung für sie deaktiviert ist. In Besprechungen, die von Amanda gehostet werden, darf niemand seinen Bildschirm oder eine Anwendung teilen – unabhängig von der Richtlinie für den Bildschirmfreigabemodus, die dem jeweiligen Benutzer zugewiesen wurde.  Daher kann Daniela ihren Bildschirm oder eine einzelne Anwendung in Amandas Besprechungen nicht freigeben.  

Derzeit können Benutzer in einer Microsoft Teams-Besprechung keine Videos abspielen oder ihren Bildschirm freigeben, wenn sie Google Chrome verwenden.

## <a name="allow-a-participant-to-give-or-request-control"></a>Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert

Diese Einstellung ist eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer die Steuerung des übertragenen Desktops oder Fensters an andere Besprechungsteilnehmer übergeben kann. Um die Steuerung zu übergeben, zeigen Sie auf den oberen Bereich des Bildschirms.

Wenn diese Einstellung für den Benutzer aktiviert ist, wird die Option **Steuerung übergeben** in der oberen Leiste einer Freigabesitzung angezeigt.

![Screenshot zeigt die Option „Steuerung übergeben“.](media/meeting-policies-give-control.png)

Wenn die Einstellung für den Benutzer deaktiviert ist, ist die Option **Steuerung übergeben** nicht verfügbar.

![Screenshot zeigt, dass die Option „Steuerung übergeben“ nicht verfügbar ist.](media/meeting-policies-give-control-not-available.png)

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Bert    | Location1MeetingPolicy        | Aus   |

Daniela kann die Steuerung des freigegebenen Desktops oder Fensters an andere Teilnehmer einer von Babek organisierten Besprechung übergeben. Babek kann anderen Teilnehmern jedoch keine Kontrolle geben.

Verwenden Sie das Cmdlet "AllowParticipantGiveRequestControl", um mithilfe von PowerShell festzulegen, wer die Steuerung übergeben bzw. entsprechende Anforderungen annehmen kann.

> [!NOTE]
> Um die Steuerung über freigegebene Inhalte während der Freigabe übergeben und übernehmen zu können, müssen beide Parteien den Microsoft Teams-Desktopclient verwenden. Die Steuerung wird nicht unterstützt, wenn eine der beiden Parteien Teams in einem Browser ausführt. Dies ist auf eine technische Einschränkung zurückzuführen, die wir planen zu beheben.

## <a name="external-participants-can-give-or-request-control"></a>Externe Teilnehmer können die Steuerung übergeben oder anfordern

Diese Einstellung ist eine benutzerspezifische Richtlinie. Ob eine Organisation diese Richtlinie für einen Benutzer festgelegt hat, steuert nicht, was externe Teilnehmer tun können, unabhängig davon, was der Besprechungsorganisator festgelegt hat. Über diesen Parameter wird gesteuert, ob externen Teilnehmern die Steuerung des von jemand anderen freigegebenen Bildschirms übergeben werden kann bzw. ob sie dies anfordern können, je nachdem, was der freigebende Benutzer in den Besprechungsrichtlinien seiner Organisation festgelegt hat. Externe Teilnehmer an Microsoft Teams-Besprechungen können wie folgt kategorisiert werden:  

- Anonyme Teilnehmer
- Gäste
- Benutzer mit externem Zugriff

Gibt an, ob benutzer mit externem Zugriff andere externe Teilnehmer steuern können, während die Freigabe von den **externen Teilnehmern gesteuert wird, um die Steuerungseinstellung in ihrer Organisation zu erteilen oder anzufordern** .

Verwenden Sie das "AllowExternalParticipantGiveRequestControl"-Cmdlet, um mithilfe von PowerShell zu steuern, ob externe Teilnehmer die Steuerung übergeben oder entsprechende Anforderungen annehmen können.

### <a name="powerpoint-live"></a>PowerPoint Live

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob der Benutzer PowerPoint-Folien in einer Besprechung übertragen kann. Externe Teilnehmer, einschließlich anonymer, Gast- und externer Zugriffsbenutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy        | Aus   |

Amanda kann keine PowerPoint-Folien in Besprechungen teilen, selbst wenn sie die Besprechungsorganisatorin ist. Daniela kann PowerPoint-Folien übertragen, auch wenn die Besprechung von Amanda organisiert wurde. Amanda kann die von anderen Personen in der Besprechung übertragenen PowerPoint-Folien anzeigen, auch wenn Sie selbst keine PowerPoint-Folien übetragen kann.

## <a name="whiteboard"></a>Whiteboard

Diese Einstellung ist eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung das Whiteboard übertragen kann. Externe Teilnehmer, einschließlich anonymer, Gast- und externer Zugriffsbenutzer, erben die Richtlinie des Besprechungsorganisators.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Whiteboard|
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy        | Aus   |

Amanda kann das Whiteboard in einer Besprechung nicht teilen, selbst wenn sie die Besprechungsorganisatorin ist. Daniela kann das Whiteboard auch dann übertragen, wenn eine Besprechung von Amanda organisiert wird.

Um Whiteboard mithilfe von PowerShell zu aktivieren, legen Sie das Cmdlet IsWBFluidEnabled auf $true von [Set-SPOTenant fest.](/powershell/module/sharepoint-online/set-spotenant)

### <a name="annotation"></a>Anmerkung

Wenn Whiteboard aktiviert ist, haben Ihre Benutzer die Möglichkeit, [Anmerkungen](/office/use-annotation-while-sharing-your-screen-in-teams) zu verwenden, ein Feature, mit dem Teilnehmer zusammenarbeiten können, während sie ihren Bildschirm in einer Teams-Besprechung freigeben. Wenn Whiteboard deaktiviert ist, haben Benutzer keinen Zugriff auf Anmerkungen.

## <a name="shared-notes"></a>Freigegebene Notizen

Diese Einstellung ist eine benutzerspezifische Richtlinie. Mit dieser Einstellung wird gesteuert, ob ein Benutzer in einer Besprechung Notizen erstellen und übertragen kann. Externe Teilnehmer, einschließlich anonymer Teilnehmer, Gäste und externer Zugriff, erben die Richtlinie des Besprechungsorganisators. Die Registerkarte **Besprechungsnotizen** wird derzeit nur in Besprechungen mit weniger als 20 Teilnehmern unterstützt.

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |Freigegebene Notizen |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia   | Location1MeetingPolicy | Aus |

Daniela kann sich in Amandas Besprechungen Notizen machen, Amanda kann hingegen in keiner Besprechung Notizen machen.




## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
- [Entfernen der Microsoft Teams-Besprechungsrichtlinie "RestrictedAnonymousAccess" von Benutzern](meeting-policies-restricted-anonymous-access.md)
