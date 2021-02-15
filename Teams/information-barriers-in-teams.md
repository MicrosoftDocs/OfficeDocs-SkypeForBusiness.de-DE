---
title: Informationsbarrieren in Microsoft Teams
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: In diesem Artikel wird erläutert, was Informationsbarrieren in Microsoft Teams sind und wie sich diese auf Teams auswirken können.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94e0117e1f0956d8e3e9ae8e6bafc7feabcdf237
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196459"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

Informationsbarrieren (Information Barrieren, PSP) sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelpersonen oder Gruppen miteinander kommunizieren. Psps sind z. B. hilfreich, wenn eine Abteilung Informationen verwendet, die nicht für andere Abteilungen freigegeben werden sollten. IBs sind auch nützlich, wenn eine Gruppe isoliert werden muss oder die Kommunikation mit Personen außerhalb dieser Gruppe verhindert werden muss.

> [!NOTE]
> - Gruppen mit Informationsbarriere (Information Barrier, IB) können nicht mandantenübergreifend erstellt werden.
> - Die Verwendung von Bots, Azure Active Directory (Azure AD)-Apps und einigen APIs zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
> - Private Kanäle sind mit den von Ihnen konfigurierten RICHTLINIEN zur Einhaltung der Richtlinien zur Datenintehstung kompatibel.
> - Neu: Informationen zur Unterstützung von Barrieren für SharePoint-Websites, die mit Teams verbunden sind, finden Sie unter "Segmente", die [Microsoft Teams-Websites zugeordnet sind.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

Außerdem verhindern RICHTLINIEN für das Sicherheitsrichtlinienrichtlinien Nachschlage- und Erkennungssuchen. Wenn Sie versuchen, mit einer Person zu kommunizieren, mit der Sie nicht kommunizieren sollten, finden Sie den Benutzer nicht in der Personenauswahl.

## <a name="background"></a>Hintergrund

Der primäre Treiber für BS stammt aus der Finanzdienstleisterbranche. Die Financial Industry Regulatory Authority[(FINRA)]( https://www.finra.org)überprüft IBs und Interessenskonflikte innerhalb von Mitgliedsunternehmen und bietet Anleitungen zur Verwaltung solcher Konflikte (FINRA 2241, [Debt Research Regulatory Notice 15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


Seit der Einführung von PSP-Codes sind sie jedoch in vielen anderen Bereichen hilfreich. Weitere häufige Szenarien sind:

- Ausbildung: Schüler einer Bildungs bildungseinrichtungen können keine Kontaktdetails für Schüler/Studierende anderer Bildungseinrichtungen nachschauen.

- Legal: Aufrechterhaltung der Vertraulichkeit von Daten, die durch die Pflege eines Kunden eingeholt werden, und verhindern, dass ein Kunde darauf zugreifen kann, wenn er von demselben Unternehmen, das einen anderen Kunden repräsentiert, darauf zugreifen kann.

- Behörden: Der Zugriff auf Informationen und die Kontrolle sind auf Abteilungen und Gruppen beschränkt.

- Professionelle Dienste: Eine Gruppe von Personen in einem Unternehmen kann während eines Kundeneinsatzes nur über Gastzugriff mit einem Kunden oder einem bestimmten Kunden chatten.

Beispielsweise gehört Enrico zum Segment "Banking" und Pradeep zum Segment "Finanzratgeber". Enrico und Pradeep können nicht miteinander kommunizieren, da die IB-Richtlinie des Unternehmens die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten blockiert. Enrico und Pradeep können jedoch mit Lee in der Personalabteilung kommunizieren.

![Beispiel mit Informationsbarrieren, die die Kommunikation zwischen Segmenten verhindern](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Verwendung von Informationsbarrieren

Möglicherweise möchten Sie IBs in Situationen wie den folgenden verwenden:

- Ein Team muss daran gehindert werden, Daten mit einem bestimmten anderen Team zu kommunizieren oder zu teilen.
- Ein Team darf keine Daten kommunizieren oder mit Personen außerhalb des Teams teilen.

Der Auswertungsdienst für Informationsbarriererichtlinien bestimmt, ob eine Kommunikation den RICHTLINIEN des Dienstanbieters entspricht.

## <a name="managing-information-barrier-policies"></a>Verwalten von Richtlinien zur Informationsbarriere

IB-Richtlinien werden im Microsoft 365 Compliance Center (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter ["Definieren von Richtlinien für Informationsbarrieren".](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Bevor Sie Richtlinien einrichten oder definieren, müssen Sie die Bereichsverzeichnissuche in Microsoft Teams aktivieren. Warten Sie nach dem Aktivieren der Bereichsverzeichnissuche mindestens einige Stunden, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. Weitere Informationen finden Sie unter ["Definieren von Richtlinien zur Informationsbarriere".](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Administratorrolle "Informationsbarrieren"

Die Rolle "IB-Compliance-Verwaltung" ist verantwortlich für die Verwaltung von IB-Richtlinien. Weitere Informationen zu dieser Rolle finden Sie unter ["Berechtigungen" im Microsoft 365 Compliance Center.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Auslöser der Informationsbarriere

IB-Richtlinien werden aktiviert, wenn die folgenden Teams-Ereignisse stattfinden:

- **Mitglieder werden einem** Team hinzugefügt: Immer wenn Sie einen Benutzer zu einem Team hinzufügen, muss die Richtlinie des Benutzers anhand der RICHTLINIEN der ANDEREN Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann er alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers das Hinzufügen zum Team blockiert, wird der Benutzer bei der Suche nicht angezeigt.

    ![Screenshot der Suche nach einem neuen Mitglied, das zu einem Team hinzugefügt werden soll, und Suchen von Übereinstimmungen](media/information-barriers-add-members.png)

- **Es wird** ein neuer Chat angefordert: Jedes Mal, wenn ein Benutzer einen neuen Chat mit einem oder mehreren anderen Benutzern anfordert, wird der Chat ausgewertet, um sicherzustellen, dass er keine RICHTLINIEN des ABC verletzt. Wenn die Unterhaltung gegen eine RICHTLINIEN des ABC verstößt, wird die Unterhaltung nicht gestartet.

    Hier ist ein Beispiel für einen 1:1-Chat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der blockierten Kommunikation in einem 1:1-Chat](media/information-barriers-one-one-chat.png)

    Hier sehen Sie ein Beispiel für einen Gruppenchat.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines Gruppenchats](media/information-barriers-group-chat.png)

- **Ein Benutzer** wird zur Teilnahme an einer Besprechung eingeladen: Wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die für den Benutzer anwendbare IB-Richtlinie anhand der IB-Richtlinien ausgewertet, die für die anderen Teammitglieder gelten. Bei einem Verstoß kann der Benutzer nicht an der Besprechung teilnehmen.

    ![Screenshot mit einem in der Besprechung blockierten Benutzer](media/information-barriers-meeting.png)

- **Ein Bildschirm** wird für zwei oder mehr Benutzer freigegeben: Wenn ein Benutzer einen Bildschirm für andere Benutzer teilt, muss die Freigabe ausgewertet werden, um sicherzustellen, dass sie nicht gegen die RICHTLINIEN anderer Benutzer verstößt. Wenn gegen eine IB-Richtlinie verstoßen wird, ist die Bildschirmfreigabe nicht zulässig. 
 
    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, bevor die Richtlinie angewendet wird. 

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines Benutzerchats](media/ib-before-screen-share-policy.png)

    Hier sehen Sie ein Beispiel für die Bildschirmfreigabe, nachdem die Richtlinie angewendet wurde. Die Symbole "Bildschirmfreigabe" und "Anruf" sind nicht sichtbar.

    > [!div class="mx-imgBorder"]
    > ![Screenshot mit Benutzer zeichen mit blockierten Einstellungen](media/ib-after-screen-share-policy.png)

- Ein Benutzer startet einen Telefonanruf **in Teams:** Immer wenn ein Benutzer einen Sprachanruf (über VOIP) für einen anderen Benutzer oder eine Benutzergruppe startet, wird der Anruf ausgewertet, um sicherzustellen, dass er nicht die RICHTLINIEN der anderen Teammitglieder verletzt. Liegt ein Verstoß vor, wird der Sprachanruf blockiert.

- **Gäste in Teams** – IB-Richtlinien gelten auch für Gäste in Teams. Wenn Gäste in der globalen Adressliste Ihrer Organisation zu finden sein müssen, lesen Sie "Verwalten des Gastzugriffs [in Microsoft 365-Gruppen".](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Sobald Gäste ermittelt werden können, können Sie [IB-Richtlinien definieren.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Auswirkungen von Richtlinienänderungen auf vorhandene Chats

Wenn der ADMINISTRATOR der Sicherheitsrichtlinie Änderungen an einer Richtlinie vor nimmt oder eine Richtlinienänderung aufgrund einer Änderung am Profil eines Benutzers aktiviert wird (z. B. bei einer Jobänderung), durchsucht der Information Barrier Policy Evaluation Service automatisch die Mitglieder, um sicherzustellen, dass deren Mitgliedschaft im Team keine Richtlinien verletzt.

Wenn es einen bestehenden Chat oder eine andere Kommunikation zwischen Benutzern gibt und eine neue Richtlinie festgelegt oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandene Kommunikationen aus, um sicherzustellen, dass die Kommunikation weiterhin zulässig ist. 

- **1:1-Chat:** Wenn die Kommunikation zwischen zwei Benutzern nicht mehr zulässig ist (aufgrund der Anwendung auf einen oder beide Benutzer einer Richtlinie, die die Kommunikation blockiert), wird die weitere Kommunikation blockiert. Die vorhandenen Chatunterhaltungen werden schreibgeschützt. 

    Hier ist ein Beispiel, das zeigt, dass der Chat sichtbar ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass ein Benutzerchat verfügbar ist](media/ib-before-1-1chat-policy.png)

    Hier ist ein Beispiel, das zeigt, dass der Chat deaktiviert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzerchat deaktiviert ist](media/ib-after-1-1chat-policy.png)

- **Gruppenchat:** Wenn die Kommunikation zwischen benutzern und gruppen nicht mehr zulässig ist (z. B. weil ein Benutzer Aufträge geändert hat), kann der Benutzer – zusammen mit den anderen Benutzern, deren Teilnahme gegen die Richtlinie verstößt – aus dem Gruppenchat entfernt werden, und weitere Kommunikation mit der Gruppe wird nicht mehr zugelassen. Der Benutzer kann weiterhin alte Unterhaltungen sehen, kann aber keine neuen Unterhaltungen mit der Gruppe sehen oder daran teilnehmen. Wenn die neue oder geänderte Richtlinie, die die Kommunikation verhindert, auf mehrere Benutzer angewendet wird, werden die von der Richtlinie betroffenen Benutzer möglicherweise aus dem Gruppenchat entfernt. Sie können weiterhin alte Unterhaltungen sehen.

  In diesem Beispiel wurde Enrico in eine andere Abteilung innerhalb der Organisation verschoben und aus dem Gruppenchat entfernt.

  ![Screenshot eines Gruppenchats, aus dem ein Benutzer entfernt wurde](media/information-barriers-user-changes-job.png)

  Enrico kann keine Nachrichten mehr an den Gruppenchat senden.

  ![Screenshot der Benachrichtigung, dass keine Nachrichten an einen Gruppenchat gesendet werden können, weil der Benutzer aus der Gruppe entfernt wurde](media/information-barriers-user-changes-job-2.png)

- **Team** – Alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können vorhandene oder neue Unterhaltungen nicht mehr sehen oder daran teilnehmen.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Szenario: Ein Benutzer in einem vorhandenen Chat wird blockiert.

Derzeit kommt es bei Benutzern zu den folgenden Szenarien, wenn eine IB-Richtlinie einen anderen Benutzer blockiert:

- **Registerkarte "Personen":** Ein Benutzer kann auf der Registerkarte "Personen" keine **blockierten Benutzer** sehen.

- **Personenauswahl** – Blockierte Benutzer werden in der Personenauswahl nicht angezeigt.

    ![Screenshot von Teams, in dem der Benutzer darüber informiert wird, dass die Richtlinie die Anzeige von Informationen eines anderen Benutzers verhindert](media/information-barriers-people-picker.png)
    
- **Registerkarte "Aktivität":** Wenn ein Benutzer die Registerkarte **"Aktivität"** eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf **der Registerkarte "Aktivität"** werden nur Kanalbeiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)

    Hier ist ein Beispiel für die Ansicht der Registerkarte "Aktivität", die blockiert ist.

    > [!div class="mx-imgBorder"]
    > ![Screenshot der Registerkarte "Aktivität", die blockiert ist](media/ib-after-activity-tab-policy.png)


- **Organigramme:** Wenn ein Benutzer auf ein Organigramm zu zugegriffen hat, in dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer nicht im Organigramm angezeigt. Stattdessen wird eine Fehlermeldung angezeigt.

- **Karte** "Personen": Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer später blockiert wird, wird anderen Benutzern anstelle der Personenkarte eine Fehlermeldung angezeigt, wenn sie auf den Namen des blockierten Benutzers zeigen. Aktionen, die auf der Karte aufgelistet sind (z. B. Anrufe und Chats), stehen nicht zur Verfügung.

- **Vorgeschlagene Kontakte** – Blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte (der anfänglichen Kontaktliste, die für neue Benutzer angezeigt wird) angezeigt.

- **Chatkontakte** – Ein Benutzer kann blockierte Benutzer in der Kontaktliste von Chats sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für die blockierten Benutzer ausführen kann, besteht im Löschen der Benutzer. Der Benutzer kann auch auf den Benutzer klicken, um seine vergangene Unterhaltung zu sehen.

- **Kontakte anrufen** – Ein Benutzer kann blockierte Benutzer in der Kontaktliste der Anrufe sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für den Blockierten ausführen kann, besteht im Löschen der Benutzer.

    Hier ist ein Beispiel für einen blockierten Benutzer in der Kontaktliste für Anrufe.

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines Benutzerchats](media/ib-before-chat-contacts-policy.png)

    Hier ist ein Beispiel dafür, wie der Chat für einen Benutzer in der Anrufinhaltsliste deaktiviert wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzer den Chat blockiert hat](media/ib-after-chat-contacts-policy.png)

- **Skype-zu-Teams-Migration** – Während einer Migration von Skype for Business zu Teams werden alle Benutzer – auch diejenigen Benutzer, die von DEN RICHTLINIEN für die Richtlinien für das Unternehmen (IB) blockiert sind – zu Teams migriert. Diese Benutzer werden dann wie oben beschrieben behandelt.

## <a name="teams-policies-and-sharepoint-sites"></a>Richtlinien für Teams und SharePoint-Websites

Wenn ein Team erstellt wird, wird eine SharePoint-Website bereitgestellt und Microsoft Teams zugeordnet, um die Dateierfahrung zu ermöglichen. IB-Richtlinien werden auf dieser SharePoint-Website und -Dateien standardmäßig nicht berücksichtigt. Zum Aktivieren von #A0 hat der Administrator bereits ein Formular ausgefüllt und die Aktivierung  von #A1 auf SharePoint und OneDrive anfordern (siehe Abschnitt "Voraussetzungen" in ["Informationsbarrieren").](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) Wenn die #A0 in SharePoint und OneDrive aktiviert ist, funktionieren die #A1 auf SharePoint-Websites, die bereitgestellt werden, wenn ein Team mit Microsoft Teams erstellt wird.

**Beispiel für IB-Richtlinien** auf der SharePoint-Website eines Teams: In der Contoso Bank corporation gehört der Benutzer "Sesha@contosobank.onmicrosoft.com" zum Segment "Investment Banking", und der Benutzer "Nikita@contosobank.onmicrosoft.com" gehört zum Segment "Advisory". Die IB-Richtlinie des Unternehmens blockiert die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten.
Wenn Benutzer Sesha ein Team für das Segment "Investment Banking" erstellt, ist das Team und die SharePoint-Website, auf der es unterstützt wird, nur für Investment Banking-Benutzer zugänglich. BenutzerIn Hyperlinkta kann nicht auf diese Website zugreifen, auch wenn sie über den Websitelink verfügt.

Weitere Informationen finden Sie unter ["Verwenden von Informationsbarrieren mit SharePoint".](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Weitere Informationen zu Lizenzen und Berechtigungen, einschließlich Plänen und Preisen, finden Sie unter [Microsoft 365-Lizenzierungsrichtlinien](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)für Sicherheit und & Compliance.

## <a name="known-issues"></a>Bekannte Probleme
- **Benutzer können nicht an Ad-hoc-Besprechungen** teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Besprechungen teilnehmen, wenn die Größe der Teilnehmerliste der Besprechung größer ist als die Grenzwerte für die Teilnahme an [Besprechungen.](limits-specifications-teams.md) Die Ursache dafür ist, dass ESA-Prüfungen darauf beruhen, ob Benutzer zu einer Besprechungschatliste hinzugefügt werden können, und nur, wenn sie zur Liste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Ein Benutzer, der einer Besprechung beitritt, fügt den Benutzer einmal zur Liste hinzu. daher kann sich die Mannschaftsliste bei Besprechungsserien schnell füllen. Sobald die Chatliste die Teilnahmelimits für Besprechungen erreicht [hat,](limits-specifications-teams.md)können der Besprechung keine weiteren Benutzer hinzugefügt werden. Wenn IB für den Mandanten aktiviert ist und die Chatliste für eine Besprechung voll ist, können neue Benutzer (diejenigen Benutzer, die noch nicht in der Liste vorhanden sind) nicht an der Besprechung teilnehmen. Wenn JEDOCH IB für den Mandanten nicht aktiviert ist und die Liste der Besprechungschats voll ist, können neue Benutzer (diejenigen Benutzer, die noch nicht in der Liste vorhanden sind) an der Besprechung teilnehmen, obwohl die Chatoption in der Besprechung nicht angezeigt wird. Eine kurzfristige Lösung besteht im Entfernen inaktiver Mitglieder aus der Liste der Besprechungschats, um Platz für neue Benutzer zu schaffen. Wir werden jedoch die Anzahl der Besprechungschats zu einem späteren Zeitpunkt erhöhen.

- **Benutzer können nicht an** Kanalbesprechungen teilnehmen: Wenn IB-Richtlinien aktiviert sind, dürfen Benutzer nicht an Kanalbesprechungen teilnehmen, wenn sie kein Mitglied des Teams sind. Die Ursache dafür ist, dass ESA-Prüfungen darauf beruhen, ob Benutzer zu einer Besprechungschatliste hinzugefügt werden können, und nur, wenn sie zur Liste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Der Chatthread in einer Kanalbe besprechung steht nur Mitgliedern des Teams/Kanals zur Verfügung, und Nichtmitglieder können den Chatthread nicht sehen oder darauf zugreifen. Wenn IB für den Mandanten aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teilnehmen, kann dieser Benutzer nicht an der Besprechung teilnehmen. Wenn JEDOCH IB  für den Mandanten nicht aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung zu teilnehmen, kann der Benutzer an der Besprechung teilnehmen, aber die Chatoption wird in der Besprechung nicht angezeigt.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zu EBs finden Sie unter ["Informationsbarrieren".](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Informationen zum Einrichten von IB-Richtlinien finden Sie unter ["Definieren von Richtlinien für Informationsbarrieren".](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Informationen zum Bearbeiten oder Entfernen von RICHTLINIEN zur Informationsbarriere finden Sie unter ["Bearbeiten (oder Entfernen) von Informationsbarriererichtlinien".](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>Verfügbarkeit
- Das Feature ist in unserer öffentlichen Cloud verfügbar. Im Januar 2021 haben wir Informationsbarrieren in der GCC-Cloud auf den Markt gemacht.
- Das Feature ist in den "GCCH"- und "DOD"-Wolken noch nicht verfügbar.
