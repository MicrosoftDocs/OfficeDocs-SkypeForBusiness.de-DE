---
title: Informationsbarrieren in Microsoft Teams
description: In diesem Artikel wird erläutert, was Informationsbarrieren in Microsoft Teams sind und wie sie sich auf Ihre Teams.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1cdb474bfab7d6f8f6cb54c4d93a225e844e1b3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729154"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

Informationsbarrieren (Information Barrieren, IBs) sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelpersonen oder Gruppen miteinander kommunizieren. PSP-Dateien sind z. B. hilfreich, wenn eine Abteilung Informationen verwendet, die nicht für andere Abteilungen freigegeben werden sollten. PSP-Codes sind auch hilfreich, wenn eine Gruppe isoliert oder daran gehindert werden muss, mit Personen außerhalb dieser Gruppe zu kommunizieren.

>[!NOTE]
>- IB(Information Barrier)-Gruppen können nicht mandantenübergreifend erstellt werden.
>- Die Verwendung von Bots, Azure Active Directory (Azure AD)-Apps, APIs zum Senden von Aktivitätsfeedbenachrichtigungen und einige APIs zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
>- Private Kanäle sind mit den von Ihnen konfigurierten IB-Richtlinien kompatibel.
>- Neu: Informationen zur Unterstützung von Barrieren für SharePoint-Websites, die mit Teams verbunden sind, finden Sie unter Segmente, die mit Microsoft Teams [sind.](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

IB-Richtlinien verhindern auch Nachschlage- und Erkennungssuchen. Wenn Sie versuchen, mit einer Person zu kommunizieren, mit der Sie nicht kommunizieren sollten, finden Sie den Benutzer nicht in der Personenauswahl.

## <a name="background"></a>Hintergrund

Der primäre Treiber für PSP-Daten stammt aus der Finanzdienstleisterbranche. Die Financial Industry Regulatory Authority[(FINRA)]( https://www.finra.org)überprüft IBs und Interessenskonflikte innerhalb von Mitgliedsunternehmen und bietet Anleitungen zum Verwalten solcher Konflikte (FINRA 2241, [Debt Research Regulatory Notice 15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)

Seit der Einführung von PSP-Codes finden sie jedoch in vielen anderen Bereichen hilfreich. Weitere häufige Szenarien sind:

- Bildung: Schüler in einer Schule können keine Kontaktdetails für Schüler/Studenten anderer Bildungseinrichtungen nachschauen.

- Legal: Aufrechterhalten der Vertraulichkeit der Daten, die sich ein Kunde von einem Kunden errät, und verhindern, dass auf diese Daten durch eine Anwaltskanzlei zugegriffen wird, die einen anderen Kunden repräsentiert.

- Behörden: Der Zugriff auf Informationen und die Steuerung sind auf Abteilungen und Gruppen beschränkt.

- Professional: Eine Gruppe von Personen in einem Unternehmen kann während eines Kundeneinsatzes nur über Gastzugriff mit einem Kunden oder einem bestimmten Kunden chatten.

Beispielsweise gehört Enrico zum Segment Banking und Pradeep zum Segment Finanzratgeber. Enrico und Pradeep können nicht miteinander kommunizieren, da die IB-Richtlinie der Organisation die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten blockiert. Enrico und Pradeep können jedoch mit Lee in der Personalabteilung kommunizieren.

![Beispiel für Informationsbarrieren, die die Kommunikation zwischen Segmenten verhindern.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Verwendung von Informationsbarrieren

Sie können PSP in Situationen wie den folgenden verwenden:

- Ein Team muss an der Kommunikation oder Freigabe von Daten an ein bestimmtes anderes Team gehindert werden.
- Ein Team darf keine Daten kommunizieren oder mit Personen außerhalb des Teams teilen.

Der Auswertungsdienst für Informationsbarriererichtlinien bestimmt, ob eine Kommunikation den IB-Richtlinien entspricht.

## <a name="managing-information-barrier-policies"></a>Verwalten von Informationsbarriererichtlinien

IB-Richtlinien werden im Microsoft 365 Compliance Center (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren.](/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Bevor Sie Richtlinien einrichten oder definieren, müssen Sie die Verzeichnissuche mit Bereichsbereich in Microsoft Teams. Warten Sie nach dem Aktivieren der Bereichssuche mindestens ein paar Stunden, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. Weitere Informationen finden Sie unter [Definieren von Informationsbarriererichtlinien.](/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Administratorrolle "Informationsbarrieren"

Die Rolle "IB Compliance Management" ist für die Verwaltung von IB-Richtlinien zuständig. Weitere Informationen zu dieser Rolle finden Sie unter [Berechtigungen im Microsoft 365 Compliance Center.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Auslöser der Informationsbarriere

IB-Richtlinien werden aktiviert, wenn die Teams Ereignisse stattfinden:

- **Mitglieder werden einem** Team hinzugefügt: Immer wenn Sie einen Benutzer zu einem Team hinzufügen, muss die Richtlinie des Benutzers anhand der IB-Richtlinien anderer Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann er alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers das Hinzufügen zum Team blockiert, wird der Benutzer bei der Suche nicht angezeigt.

    ![Screenshot der Suche nach einem neuen Mitglied, das zu einem Team hinzugefügt werden soll, und der Suche nach keinen Übereinstimmungen](media/information-barriers-add-members.png)

- **Ein neuer Chat** wird angefordert: Jedes Mal, wenn ein Benutzer einen neuen Chat mit einem oder mehreren Benutzern anfordert, wird der Chat ausgewertet, um sicherzustellen, dass er keine IB-Richtlinien verletzt. Wenn die Unterhaltung eine IB-Richtlinie verletzt, wird die Unterhaltung nicht gestartet.

    Hier ist ein Beispiel für einen 1:1-Chat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot mit blockierter Kommunikation in einem 1:1-Chat.](media/information-barriers-one-one-chat.png)

    Hier ist ein Beispiel für einen Gruppenchat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Gruppenchats](media/information-barriers-group-chat.png)

- **Ein Benutzer wird** zur Teilnahme an einer Besprechung eingeladen: Wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die für den Benutzer geltende IB-Richtlinie anhand der IB-Richtlinien ausgewertet, die für die anderen Teammitglieder gelten. Wenn ein Verstoß vor besteht, kann der Benutzer nicht an der Besprechung teilnehmen.

    ![Screenshot mit dem in der Besprechung blockierten Benutzer.](media/information-barriers-meeting.png)

- **Ein Bildschirm wird für** zwei oder mehr Benutzer freigegeben: Wenn ein Benutzer einen Bildschirm für andere Benutzer teilt, muss die Freigabe ausgewertet werden, um sicherzustellen, dass sie nicht gegen die IB-Richtlinien anderer Benutzer verstößt. Wenn eine IB-Richtlinie verletzt wird, ist die Bildschirmfreigabe nicht zulässig.

    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, bevor die Richtlinie angewendet wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines Benutzerchats](media/ib-before-screen-share-policy.png)

    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, nachdem die Richtlinie angewendet wurde. Die Symbole für Bildschirmfreigabe und Anruf sind nicht sichtbar.

    > [!div class="mx-imgBorder"]
    > ![Screenshot mit Einem Zeichen des Benutzers mit blockierten Einstellungen](media/ib-after-screen-share-policy.png)

- Ein Benutzer platziert einen Telefonanruf **in Teams:** Immer wenn ein Benutzer einen Sprachanruf (über VOIP) für einen anderen Benutzer oder eine Benutzergruppe initiiert, wird der Anruf ausgewertet, um sicherzustellen, dass er nicht gegen die IB-Richtlinien anderer Teammitglieder verstößt. Wenn ein Verstoß vor liegt, wird der Sprachanruf blockiert.

- **Gäste in Teams** – IB-Richtlinien gelten auch für Gäste in Teams. Wenn Gäste in der globalen Adressliste Ihrer Organisation ermittelt werden müssen, lesen Sie Verwalten des Gastzugriffs [in Microsoft 365 Gruppen.](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Sobald Gäste ermittelt werden können, können Sie [IB-Richtlinien definieren.](/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Auswirkungen von Richtlinienänderungen auf vorhandene Chats

Wenn der IB-Richtlinienadministrator Änderungen an einer Richtlinie vor nimmt oder eine Richtlinienänderung aufgrund einer Änderung am Profil eines Benutzers (z. B. bei einer Auftragsänderung) aktiviert wird, durchsucht der Auswertungsdienst für Informationsbarriererichtlinien automatisch die Mitglieder, um sicherzustellen, dass deren Mitgliedschaft im Team keine Richtlinien verletzt.

Wenn es einen vorhandenen Chat oder eine andere Kommunikation zwischen Benutzern gibt und eine neue Richtlinie festgelegt oder eine vorhandene Richtlinie geändert wurde, wertet der Dienst vorhandene Kommunikationen aus, um sicherzustellen, dass die Kommunikation weiterhin stattfinden darf. 

- **1:1 Chat:** Wenn die Kommunikation zwischen zwei Benutzern nicht mehr zulässig ist (aufgrund der Anwendung auf einen oder beide Benutzer einer Richtlinie, die Kommunikation blockiert), wird die weitere Kommunikation blockiert. Ihre vorhandenen Chatunterhaltungen werden schreibgeschützt.

    Hier ist ein Beispiel, das zeigt, dass der Chat sichtbar ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass ein Benutzerchat verfügbar ist.](media/ib-before-1-1chat-policy.png)

    Hier ist ein Beispiel, das zeigt, dass der Chat deaktiviert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzerchat deaktiviert ist.](media/ib-after-1-1chat-policy.png)

- **Gruppenchat** – Wenn die Kommunikation zwischen Benutzern zu einer Gruppe nicht mehr zulässig ist (z. B. weil ein Benutzer Aufträge geändert hat), kann der Benutzer – zusammen mit den anderen Benutzern, deren Beteiligung gegen die Richtlinie verstößt – aus dem Gruppenchat entfernt werden, und weitere Kommunikation mit der Gruppe wird nicht zugelassen. Der Benutzer kann weiterhin alte Unterhaltungen sehen, kann aber keine neuen Unterhaltungen mit der Gruppe sehen oder daran teilnehmen. Wenn die neue oder geänderte Richtlinie, die Kommunikation verhindert, auf mehrere Benutzer angewendet wird, werden die von der Richtlinie betroffenen Benutzer möglicherweise aus dem Gruppenchat entfernt. Sie können weiterhin alte Unterhaltungen sehen.

  In diesem Beispiel wurde Enrico in eine andere Abteilung innerhalb der Organisation verschoben und aus dem Gruppenchat entfernt.

  ![Screenshot eines Gruppenchats, aus dem ein Benutzer entfernt wurde](media/information-barriers-user-changes-job.png)

  Enrico kann keine Nachrichten mehr an den Gruppenchat senden.

  ![Screenshot der Fehlermeldung, dass keine Nachrichten an einen Gruppenchat gesendet werden können, weil der Benutzer aus der Gruppe entfernt wurde.](media/information-barriers-user-changes-job-2.png)

- **Team** – Alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können vorhandene oder neue Unterhaltungen nicht sehen oder daran teilnehmen.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Szenario: Ein Benutzer in einem vorhandenen Chat wird blockiert.

Derzeit kommt es zu den folgenden Szenarien, wenn eine IB-Richtlinie einen anderen Benutzer blockiert:

- **Registerkarte** "Personen": Ein Benutzer kann auf der Registerkarte "Personen" keine **blockierten Benutzer** sehen.

- **Personenauswahl** – Blockierte Benutzer werden in der Personenauswahl nicht angezeigt.

    ![Screenshot des Teams, mit dem der Benutzer darüber informiert wird, dass die Richtlinie die Anzeige von Informationen eines anderen Benutzers verhindert.](media/information-barriers-people-picker.png)

- **Registerkarte Aktivität:** Wenn ein Benutzer die Registerkarte **Aktivität eines** blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf **der Registerkarte** Aktivität werden nur Kanalbeiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)

    Hier ist ein Beispiel für die Ansicht der Registerkarte "Aktivität", die blockiert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Registerkarte "Aktivität", die blockiert ist.](media/ib-after-activity-tab-policy.png)

- **Organigramme:** Wenn ein Benutzer auf ein Organigramm zutritt, in dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer nicht im Organigramm angezeigt. Stattdessen wird eine Fehlermeldung angezeigt.

- **Karte** "Personen": Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer später blockiert wird, wird anderen Benutzern anstelle der Personenkarte eine Fehlermeldung angezeigt, wenn sie auf den Namen des blockierten Benutzers zeigen. Aktionen, die auf der Karte aufgelistet sind (z. B. Anrufe und Chats), sind nicht verfügbar.

- **Vorgeschlagene Kontakte–** Blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte (der anfänglichen Kontaktliste, die für neue Benutzer angezeigt wird) angezeigt.

- **Chatkontakte–** Ein Benutzer kann blockierte Benutzer in der Kontaktliste von Chats sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für die blockierten Benutzer ausführen kann, besteht im Löschen der Benutzer. Der Benutzer kann auch auf den Benutzer klicken, um seine vergangene Unterhaltung zu sehen.

- **Anrufe an** Kontakte: Ein Benutzer kann blockierte Benutzer in der Kontaktliste von Anrufen sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für den Blockierungsbenutzer ausführen kann, ist das Löschen.

    Hier ist ein Beispiel für einen blockierten Benutzer in der Kontaktliste "Anrufe".

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Benutzerchats](media/ib-before-chat-contacts-policy.png)

    Hier ist ein Beispiel für den Chat, der für einen Benutzer in der Liste "Anrufinhalte" deaktiviert wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzer den Chat blockiert hat.](media/ib-after-chat-contacts-policy.png)

- **Skype** zu Teams Migrationen – Während einer Migration von Skype for Business zu Teams werden alle Benutzer – auch diejenigen Benutzer, die von den IB-Richtlinien blockiert werden – zu Teams. Diese Benutzer werden dann wie oben beschrieben behandelt.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams von Richtlinien und SharePoint Websites

Wenn ein Team erstellt wird, wird eine SharePoint für die Dateierfahrung bereitgestellt und Microsoft Teams zugeordnet. Richtlinien zur Informationsbarriere werden auf dieser Website SharePoint Dateien standardmäßig nicht berücksichtigt. Um Informationsbarrieren in SharePoint und OneDrive zu aktivieren, folgen Sie den Anleitungen und Schritten unter Verwenden von Informationsbarrieren [mit](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) SharePoint Thema.

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Weitere Informationen zu Lizenzen und Berechtigungen, einschließlich Plänen und Preisen Microsoft 365, finden Sie unter Lizenzierungsrichtlinien für & [Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="known-issues"></a>Bekannte Probleme

- **Benutzer können nicht an Ad-hoc-Besprechungen** teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Besprechungen teilnehmen, wenn die Größe der Teilnehmerliste größer ist als die Teilnahmebeschränkungen für [Besprechungen.](limits-specifications-teams.md) Die Ursache hierauf ist, dass IB-Prüfungen darauf beruhen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können und nur dann, wenn sie der Liste hinzugefügt werden können, an der Besprechung teilnehmen können. Ein Benutzer, der einer Besprechung beitritt, fügt den Benutzer einmal zur Liste hinzu. daher kann die Mannschaftsliste schnell auffüllen. Sobald die Chatliste die Teilnahmebeschränkungen für Besprechungen erreicht [hat,](limits-specifications-teams.md)können der Besprechung keine weiteren Benutzer hinzugefügt werden. Wenn IB für den Mandanten aktiviert ist und die Chatliste für eine Besprechung voll ist, können neue Benutzer (benutzer, die noch nicht in der Liste vorhanden sind) nicht an der Besprechung teilnehmen. Wenn jedoch IB für den Mandanten nicht aktiviert ist und die Liste der Besprechungschats voll ist, können neue Benutzer (benutzer, die noch nicht in der Liste vorhanden sind) an der Besprechung teilnehmen, obwohl die Chatoption in der Besprechung nicht angezeigt wird. Eine kurzfristige Lösung besteht im Entfernen inaktiver Mitglieder aus der Liste der Besprechungschats, um Platz für neue Benutzer zu schaffen. Wir werden jedoch die Größe der Besprechungschat-Liste zu einem späteren Zeitpunkt erhöhen.
- **Benutzer können nicht an Kanalbesprechungen** teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Kanalbesprechungen teilnehmen, wenn sie kein Mitglied des Teams sind. Die Ursache hierauf ist, dass IB-Prüfungen darauf beruhen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können und nur dann, wenn sie der Liste hinzugefügt werden können, an der Besprechung teilnehmen können. Der Chatthread in einer Kanalbe besprechung steht nur Mitgliedern des Teams/Kanals zur Verfügung, und Nichtmitglieder können den Chatthread nicht sehen oder darauf zugreifen. Wenn IB für den Mandanten aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teilnehmen, kann dieser Benutzer der Besprechung nicht beitreten. Wenn JEDOCH IB  für den Mandanten nicht aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teilnehmen, kann der Benutzer an der Besprechung teilnehmen, aber die Chatoption wird in der Besprechung nicht angezeigt.
- **Teambesitzer** werden nicht entfernt: Wenn eine neue IB-Richtlinie angewendet wird, die zu zwei oder mehr konfliktesenden Segmenten in einem Teams-Kanal führt, erhalten die Segmente mit Teambesitzern eine höhere Einstellung, und andere Segmentbenutzer werden entfernt. Zu diesem Zeitpunkt werden Teambesitzer auch dann nicht entfernt, wenn sie im Konflikt mit anderen Besitzern/Benutzern stehen. Mandantenadministratoren und andere Kanalbesitzer müssen widersprüchliche Besitzer manuell entfernen.
- **Maximale Anzahl der in einem Mandanten zulässigen** Segmente: Jeder Mandant kann beim Konfigurieren von IB-Richtlinien bis zu 100 Segmente einrichten. Es gibt keine Beschränkung bei der Anzahl der Richtlinien, die konfiguriert werden können.

- **IB-Richtlinien funktionieren** für Verbundbenutzer nicht: Wenn Sie einen Verbund mit externen Mandanten zulassen, sind die Benutzer dieser Mandanten durch IB-Richtlinien nicht eingeschränkt. Wenn Benutzer Ihrer Organisation an einem Von externen Verbundbenutzern organisierten Chat oder einer Besprechung teilnehmen, schränken die IB-Richtlinien auch nicht die Kommunikation zwischen den Benutzern Ihrer Organisation ein.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zu PSP-Daten finden Sie unter [Informationsbarrieren.](/office365/securitycompliance/information-barriers)

- Informationen zum Einrichten von IB-Richtlinien finden Sie unter [Definieren von Richtlinien für Informationsbarrieren.](/office365/securitycompliance/information-barriers-policies)

- Informationen zum Bearbeiten oder Entfernen von IB-Richtlinien finden Sie unter [Bearbeiten (oder Entfernen) von Informationsbarriererichtlinien.](/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>Verfügbarkeit

- Das Feature ist in unserer öffentlichen Cloud verfügbar. Im Januar 2021 haben wir Informationsbarrieren in der GCC haben.
- Das Feature ist in GGCH und DOD-Wolken noch nicht verfügbar.
