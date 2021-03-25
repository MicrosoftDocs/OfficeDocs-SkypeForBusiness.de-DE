---
title: Informationsbarrieren in Microsoft Teams
description: In diesem Artikel wird erläutert, was Informationsbarrieren in Microsoft Teams sind und wie sich diese auf Teams auswirken können.
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
ms.openlocfilehash: 79a1a416e0d868129e2d78f305cfe32efb527d53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120646"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

Informationsbarrieren (IBs) sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelne oder Gruppen miteinander kommunizieren. IBs sind nützlich, wenn beispielsweise eine Abteilung Informationen abhanden kommt, die nicht für andere Abteilungen freigegeben werden sollten. IBs sind auch nützlich, wenn eine Gruppe isoliert werden oder an der Kommunikation mit personen außerhalb dieser Gruppe gehindert werden muss.

>[!NOTE]
>- Information Barrier (IB)-Gruppen können nicht mandantenübergreifend erstellt werden.
>- Die Verwendung von Bots, Azure Active Directory(Azure AD)-Apps und einigen APIs zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
>- Private Kanäle sind mit den von Ihnen konfigurierten IB-Richtlinien kompatibel.
>- Neu: Informationen zur Unterstützung von Barrieren für SharePoint-Websites, die mit Teams verbunden sind, finden Sie unter Segmente, die [Microsoft Teams-Websites zugeordnet sind.](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

Ib-Richtlinien verhindern außerdem Nachschlage- und -ermittlungen. Wenn Sie versuchen, mit einer Person zu kommunizieren, mit der Sie nicht kommunizieren sollten, finden Sie den Benutzer in der Personenauswahl nicht.

## <a name="background"></a>Hintergrund

Der Haupttreiber für IBs stammt aus der Finanzbranche. Die Financial Industry Regulatory Authority[(FINRA)]( https://www.finra.org)überprüft IBs und Interessenkonflikte innerhalb von Mitgliedsfirmen und bietet Anleitungen zur Verwaltung solcher Konflikte (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).

Seit der Einführung von IBs haben sich diese jedoch in vielen anderen Bereichen als nützlich herausgefunden. Weitere häufige Szenarien sind:

- Ausbildung: Schüler/Studenten in einer Schule können keine Kontaktdetails für Schüler/Studenten anderer Bildungseinrichtungen nachschauen.

- Legal: Wahrung der Vertraulichkeit von Daten, die vom Anwalt eines Mandanten eingeholt werden, und Verhindern, dass ein Anwalt für dieselbe Firma, die einen anderen Mandanten repräsentiert, darauf zugreifen kann.

- Behörden: Der Zugriff auf Informationen und die Kontrolle sind über Abteilungen und Gruppen beschränkt.

- Professionelle Dienste: Eine Gruppe von Personen in einem Unternehmen kann während eines Kundeneinsatzes nur über den Gastzugriff mit einem Kunden oder einem bestimmten Kunden chatten.

Beispielsweise gehört Enrico zum Segment Bankwesen und Pradeep zum Segment Finanzberater. Enrico und Pradeep können nicht miteinander kommunizieren, da die IB-Richtlinie der Organisation die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten blockiert. Enrico und Pradeep können jedoch mit Lee in hr kommunizieren.

![Beispiel für Informationsbarrieren, die die Kommunikation zwischen Segmenten verhindern](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Verwendung von Informationsbarrieren

Möglicherweise möchten Sie IBs in Situationen wie den folgenden verwenden:

- Ein Team muss daran gehindert werden, Daten mit einem bestimmten anderen Team zu kommunizieren oder zu teilen.
- Ein Team darf keine Daten mit personen außerhalb des Teams kommunizieren oder teilen.

Der Information Barrier Policy Evaluation Service bestimmt, ob eine Kommunikation mit DEN RICHTLINIEN für die Informationsbarriere in Einklang steht.

## <a name="managing-information-barrier-policies"></a>Verwalten von Richtlinien für Informationsbarrieren

IB-Richtlinien werden im Microsoft 365 Compliance Center (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Bevor Sie Richtlinien einrichten oder definieren, müssen Sie die Bereichsverzeichnissuche in Microsoft Teams aktivieren. Warten Sie nach dem Aktivieren der Bereichsverzeichnissuche mindestens einige Stunden, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. Weitere Informationen finden Sie unter [Definieren von Informationsbarriererichtlinien](/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Administratorrolle für Informationsbarrieren

Die Rolle "IB Compliance Management" ist für die Verwaltung von IB-Richtlinien zuständig. Weitere Informationen zu dieser Rolle finden Sie unter [Berechtigungen im Microsoft 365 Compliance Center.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Auslöser der Informationsbarriere

IB-Richtlinien werden aktiviert, wenn die folgenden Teams-Ereignisse stattfinden:

- **Mitglieder werden einem** Team hinzugefügt: Immer wenn Sie einem Team einen Benutzer hinzufügen, muss die Richtlinie des Benutzers anhand der RICHTLINIEN der anderen Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann er alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers verhindert, dass er dem Team hinzugefügt wird, wird der Benutzer bei der Suche nicht angezeigt.

    ![Screenshot der Suche nach einem neuen Mitglied, das einem Team hinzugefügt werden soll, und Suchen nach keine Übereinstimmungen](media/information-barriers-add-members.png)

- **Ein neuer Chat** wird angefordert: Jedes Mal, wenn ein Benutzer einen neuen Chat mit einem oder mehreren anderen Benutzern anfordert, wird der Chat ausgewertet, um sicherzustellen, dass keine IB-Richtlinien verletzt werden. Wenn die Unterhaltung gegen eine IB-Richtlinie verstößt, wird die Unterhaltung nicht gestartet.

    Hier ist ein Beispiel für einen 1:1-Chat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der blockierten Kommunikation im 1:1-Chat](media/information-barriers-one-one-chat.png)

    Hier ist ein Beispiel für einen Gruppenchat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Gruppenchats](media/information-barriers-group-chat.png)

- **Ein Benutzer wird** zur Teilnahme an einer Besprechung eingeladen: Wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die für den Benutzer anwendbare IB-Richtlinie anhand der FÜR DIE ANDEREN Teammitglieder anwendbaren RICHTLINIEN ausgewertet. Wenn ein Verstoß vor besteht, darf der Benutzer nicht an der Besprechung teilnehmen.

    ![Screenshot, der zeigt, dass der Benutzer die Besprechung blockiert hat](media/information-barriers-meeting.png)

- **Ein Bildschirm wird** für zwei oder mehr Benutzer freigegeben: Wenn ein Benutzer einen Bildschirm für andere Benutzer freigegeben hat, muss die Freigabe ausgewertet werden, um sicherzustellen, dass sie nicht gegen die RICHTLINIEN anderer Benutzer verstößt. Wenn eine IB-Richtlinie verletzt wird, ist die Bildschirmfreigabe nicht zulässig.

    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, bevor die Richtlinie angewendet wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines Benutzerchats](media/ib-before-screen-share-policy.png)

    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, nachdem die Richtlinie angewendet wurde. Die Bildschirmfreigabe- und Anrufsymbole sind nicht sichtbar.

    > [!div class="mx-imgBorder"]
    > ![Screenshot mit Benutzer-Zeichen mit blockierten Einstellungen](media/ib-after-screen-share-policy.png)

- Ein Benutzer gibt einen Telefonanruf **in Teams** ab– Immer wenn ein Benutzer einen Sprachanruf (über VOIP) für einen anderen Benutzer oder eine Benutzergruppe startet, wird der Anruf ausgewertet, um sicherzustellen, dass er nicht gegen die RICHTLINIEN anderer Teammitglieder verstößt. Wenn ein Verstoß vor liegt, wird der Sprachanruf blockiert.

- **Die Richtlinien für Gäste in Teams** – IB gelten auch für Gäste in Teams. Wenn Gäste in der globalen Adressliste Ihrer Organisation ermittelt werden müssen, lesen Sie Verwalten des Gastzugriffs [in Microsoft 365-Gruppen.](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Sobald Gäste entdeckt wurden, können Sie [IB-Richtlinien definieren.](/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Auswirkungen von Richtlinienänderungen auf vorhandene Chats

Wenn der ADMINISTRATOR einer Richtlinie Änderungen an einer Richtlinie vor nimmt oder wenn eine Richtlinienänderung aufgrund einer Änderung am Profil eines Benutzers aktiviert wird (z. B. bei einer Auftragsänderung), durchsucht der Information Barrier Policy Evaluation Service automatisch die Mitglieder, um sicherzustellen, dass ihre Mitgliedschaft im Team keine Richtlinien verletzt.

Wenn ein Chat oder eine andere Kommunikation zwischen Benutzern vorhanden ist und eine neue Richtlinie festgelegt oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandene Kommunikationen aus, um sicherzustellen, dass die Kommunikationen weiterhin zulässig sind. 

- **1:1 Chat:** Wenn die Kommunikation zwischen zwei Benutzern nicht mehr zulässig ist (aufgrund der Anwendung für einen oder beide Benutzer einer Richtlinie, die die Kommunikation blockiert), wird die weitere Kommunikation blockiert. Ihre vorhandenen Chatunterhaltungen werden schreibgeschützt.

    Hier ist ein Beispiel, das zeigt, dass der Chat sichtbar ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass benutzerchat verfügbar ist](media/ib-before-1-1chat-policy.png)

    In diesem Beispiel wird gezeigt, dass der Chat deaktiviert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzerchat deaktiviert ist](media/ib-after-1-1chat-policy.png)

- Gruppenchat **:** Wenn die Kommunikation von einem Benutzer zu einer Gruppe nicht mehr zulässig ist (z. B. weil ein Benutzer Aufträge geändert hat), kann der Benutzer – zusammen mit den anderen Benutzern, deren Teilnahme gegen die Richtlinie verstößt – aus dem Gruppenchat entfernt werden, und eine weitere Kommunikation mit der Gruppe ist nicht zulässig. Der Benutzer kann weiterhin alte Unterhaltungen sehen, aber keine neuen Unterhaltungen mit der Gruppe sehen oder daran teilnehmen. Wenn die neue oder geänderte Richtlinie, die die Kommunikation verhindert, auf mehrere Benutzer angewendet wird, werden die von der Richtlinie betroffenen Benutzer möglicherweise aus dem Gruppenchat entfernt. Sie können weiterhin alte Unterhaltungen sehen.

  In diesem Beispiel wurde Enrico in eine andere Abteilung innerhalb der Organisation verschoben und aus dem Gruppenchat entfernt.

  ![Screenshot eines Gruppenchats, aus dem ein Benutzer entfernt wurde](media/information-barriers-user-changes-job.png)

  Enrico kann keine Nachrichten mehr an den Gruppenchat senden.

  ![Screenshot, dass keine Nachrichten an den Gruppenchat gesendet werden können, da der Benutzer aus der Gruppe entfernt wurde](media/information-barriers-user-changes-job-2.png)

- **Team** – Alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können vorhandene oder neue Unterhaltungen nicht sehen oder daran teilnehmen.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Szenario: Ein Benutzer in einem vorhandenen Chat wird blockiert

Derzeit erleben Benutzer die folgenden Szenarien, wenn eine IB-Richtlinie einen anderen Benutzer blockiert:

- **Registerkarte** "Personen": Ein Benutzer kann blockierte Benutzer auf der Registerkarte **"Personen" nicht** sehen.

- **Personenauswahl** – Blockierte Benutzer werden in der Personenauswahl nicht angezeigt.

    ![Screenshot von Teams, der den Benutzer darüber informiert, dass die Richtlinie die Anzeige der Informationen eines anderen Benutzers verhindert](media/information-barriers-people-picker.png)

- **Registerkarte Aktivität:** Wenn ein Benutzer die Registerkarte **Aktivität** eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf **der Registerkarte Aktivität** werden nur Kanalbeiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)

    Hier ist ein Beispiel für die Aktivitätsregisterkartenansicht, die blockiert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Registerkarte "Aktivität", die blockiert ist](media/ib-after-activity-tab-policy.png)

- **Organigramme:** Wenn ein Benutzer auf ein Organigramm zutritt, in dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer im Organigramm nicht angezeigt. Stattdessen wird eine Fehlermeldung angezeigt.

- **Personenkarte:** Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer später blockiert wird, wird für andere Benutzer anstelle der Personenkarte eine Fehlermeldung angezeigt, wenn sie auf den Namen des blockierten Benutzers zeigen. Auf der Karte aufgeführte Aktionen (z. B. Anrufe und Chats) sind nicht verfügbar.

- **Vorgeschlagene Kontakte** – Blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte angezeigt (die erste Kontaktliste, die für neue Benutzer angezeigt wird).

- **Chatkontakte** – Ein Benutzer kann blockierte Benutzer in der Kontaktliste für Chats sehen, die blockierten Benutzer werden jedoch identifiziert. Die einzige Aktion, die der Benutzer für die blockierten Benutzer ausführen kann, besteht im Löschen. Der Benutzer kann auch auf den Benutzer klicken, um seine vergangene Unterhaltung zu sehen.

- **Anrufe an** Kontakte – Ein Benutzer kann blockierte Benutzer in der Kontaktliste für Anrufe sehen, die blockierten Benutzer werden jedoch identifiziert. Die einzige Aktion, die der Benutzer für die Blockbenutzer ausführen kann, besteht im Löschen.

    Hier ist ein Beispiel für einen blockierten Benutzer in der Kontaktliste für Anrufe.

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Benutzerchats](media/ib-before-chat-contacts-policy.png)

    Hier ist ein Beispiel für den Chat, der für einen Benutzer in der Inhaltsliste für Anrufe deaktiviert wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot mit gesperrten Benutzern im Chat](media/ib-after-chat-contacts-policy.png)

- **Skype-zu-Teams-Migration** – Während einer Migration von Skype for Business zu Teams werden alle Benutzer – auch die Benutzer, die von DEN RICHTLINIEN blockiert werden – zu Teams migriert. Diese Benutzer werden dann wie oben beschrieben behandelt.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams-Richtlinien und SharePoint-Websites

Wenn ein Team erstellt wird, wird eine SharePoint-Website für die Dateierfahrung bereitgestellt und Microsoft Teams zugeordnet. IB-Richtlinien werden auf dieser SharePoint-Website und -Dateien standardmäßig nicht berücksichtigt. Um #A0 zu aktivieren, hat der Administrator bereits ein Formular ausgefüllt, in dem  er fordert, dass #A1 in SharePoint und OneDrive aktiviert werden (siehe Abschnitt Voraussetzungen unter [Informationsbarrieren](/sharepoint/information-barriers#prerequisites)). Wenn die #A0 in SharePoint und OneDrive aktiviert ist, funktionieren die #A1 auf SharePoint-Websites, die bereitgestellt werden, wenn ein Team mit Microsoft Teams erstellt wird.

**Beispiel für IB-Richtlinien** auf der SharePoint-Website eines Teams: In contoso bank corporation gehört der Benutzer "Sesha@contosobank.onmicrosoft.com" zum Segment Investment Banking, und der Benutzer "Nikita@contosobank.onmicrosoft.com" gehört zum Segment Advisory. Die IB-Richtlinie der Organisation blockiert die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten.
Wenn Benutzer Sesha ein Team für das InvestmentBanking-Segment erstellt, ist das Team und die SharePoint-Website, auf der sie unterstützt wird, nur für InvestmentBanking-Benutzer zugänglich. Der Benutzer Kann nicht auf diese Website zugreifen, auch wenn er über den Websitelink verfügt.

Weitere Informationen finden Sie unter [Verwenden von Informationsbarrieren mit SharePoint](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Weitere Informationen zu Lizenzen und Berechtigungen, einschließlich Plänen und Preisen, finden Sie unter Microsoft 365-Lizenzierungsleitfäden für Sicherheit [und & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="known-issues"></a>Bekannte Probleme

- Benutzer können nicht an **Ad-hoc-Besprechungen** teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Besprechungen teilnehmen, wenn die Größe der Besprechungsliste größer als die Besprechungsteilnehmergrenzwerte [ist.](limits-specifications-teams.md) Die Ursache ist, dass DIE ÜBERPRÜFUNGen davon abhingen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können, und nur wenn sie zur Liste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Ein Benutzer, der einmal an einer Besprechung teiln beitritt, fügt den Benutzer zur Liste hinzu. daher kann sich die Liste für besprechungsserienbesprechende Besprechungen schnell füllen. Sobald die Chatliste die Besprechungsteilnehmergrenzwerte erreicht [hat,](limits-specifications-teams.md)dürfen der Besprechung keine weiteren Benutzer hinzugefügt werden. Wenn IB für den Mandanten aktiviert ist und die Chatliste für eine Besprechung voll ist, dürfen neue Benutzer (diese Benutzer, die noch nicht in der Liste sind) nicht an der Besprechung teilnehmen. Wenn JEDOCH IB für den Mandanten nicht aktiviert ist und die Liste der Besprechungschats voll ist, dürfen neue Benutzer (diese Benutzer, die noch nicht in der Liste sind) an der Besprechung teilnehmen, obwohl die Chatoption in der Besprechung nicht angezeigt wird. Eine kurzfristige Lösung besteht in der Entfernung inaktiver Mitglieder aus der Besprechungschatliste, um Platz für neue Benutzer zu schaffen. Wir werden jedoch die Größe der Besprechungschatliste zu einem späteren Zeitpunkt erhöhen.
- **Benutzer können nicht an** Kanalbesprechungen teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Kanalbesprechungen teilnehmen, wenn sie kein Mitglied des Teams sind. Die Ursache ist, dass DIE ÜBERPRÜFUNGen davon abhingen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können, und nur wenn sie zur Liste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Der Chatthread in einer Kanalbe besprechung ist nur für Team-/Kanalmitglieder verfügbar, und Nichtmitglieder können den Chatthread nicht sehen oder darauf zugreifen. Wenn IB für den Mandanten aktiviert ist und ein Nichtteammitglied versucht, an einer Kanalbesprechung teil zu nehmen, darf dieser Benutzer nicht an der Besprechung teilnehmen. Wenn JEDOCH IB  für den Mandanten nicht aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teil zu nehmen, darf der Benutzer an der Besprechung teilnehmen– die Chatoption wird in der Besprechung jedoch nicht angezeigt.
- **Teambesitzer** werden nicht entfernt: Wenn eine neue IB-Richtlinie angewendet wird, die zu zwei oder mehr widersprüchlichen Segmenten in einem Teams-Kanal führt, erhalten die Segmente mit Teambesitzern eine höhere Einstellung, und andere Segmentbenutzer werden entfernt. Außerdem werden Teambesitzer zu diesem Zeitpunkt nicht entfernt, auch wenn sie mit anderen Besitzern/Benutzern in Konflikt stehen. Mandantenadministratoren und andere Kanalbesitzer müssen widersprüchliche Besitzer manuell entfernen.
- **Maximale Anzahl von Segmenten, die in** einem Mandanten zulässig sind: Jeder Mandant kann beim Konfigurieren von IB-Richtlinien bis zu 100 Segmente einrichten. Die Anzahl der Richtlinien, die konfiguriert werden können, ist nicht begrenzt.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zu IBs finden Sie unter [Informationsbarrieren](/office365/securitycompliance/information-barriers).

- Informationen zum Einrichten von RICHTLINIEN finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](/office365/securitycompliance/information-barriers-policies).

- Informationen zum Bearbeiten oder Entfernen von IB-Richtlinien finden Sie unter [Bearbeiten (oder Entfernen) von Informationsbarriererichtlinien.](/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>Verfügbarkeit

- Das Feature ist in unserer öffentlichen Cloud verfügbar. Im Januar 2021 haben wir informationsbarrieren in der GCC-Cloud ein Roll-out durchgeführt.
- Das Feature ist in den GcCH- und DOD-Wolken noch nicht verfügbar.