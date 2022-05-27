---
title: Informationsbarrieren in Microsoft Teams
description: In diesem Artikel wird erläutert, wie Informationsbarrieren in Microsoft Teams unterstützt werden.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
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
ms.openlocfilehash: 38698179e2a3b4c6ca402190c98f89f329820d6e
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675407"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

[Microsoft Purview Informationsbarrieren (IBs](/microsoft-365/compliance/information-barriers)) sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelpersonen oder Gruppen miteinander kommunizieren. IBs sind nützlich, wenn beispielsweise eine Abteilung Informationen verarbeitet, die nicht für andere Abteilungen freigegeben werden sollten. IBs sind auch hilfreich, wenn eine Gruppe isoliert werden muss oder verhindert werden muss, dass sie mit personen außerhalb dieser Gruppe kommuniziert. Freigegebene Kanäle in Microsoft Teams werden von Informationsbarrieren unterstützt. Je nach Art der Freigabe können Richtlinien für Informationsbarrieren die Freigabe auf bestimmte Weise einschränken. Weitere Informationen zum Verhalten freigegebener Kanäle und Informationsbarrieren finden Sie unter [Informationsbarrieren und freigegebene Kanäle](information-barriers-shared-channels.md).

Für Microsoft Teams können Informationsbarrieren die folgenden Arten von nicht autorisierten Zusammenarbeiten ermitteln und verhindern:

- Hinzufügen eines Benutzers zu einem Team oder Kanal
- Benutzerzugriff auf Team- oder Kanalinhalte
- Benutzerzugriff auf 1:1- und Gruppenchats
- Benutzerzugriff auf Besprechungen
- Verhindert Nachschlagevorgänge und Ermittlungen. Benutzer werden in der Personenauswahl nicht angezeigt.

>[!NOTE]
>- Gruppen von Informationsbarrieren können nicht mandantenübergreifend erstellt werden.
>- Die Verwendung von Bots, Azure Active Directory(Azure AD)-Apps, APIs zum Senden von Aktivitätsfeedbenachrichtigungen und einigen APIs zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
>- Private Kanäle sind mit den von Ihnen konfigurierten Richtlinien für Informationsbarrieren kompatibel.
>- Informationen zur Unterstützung von Barrieren für SharePoint Websites, die mit Teams verbunden sind, finden Sie unter [Segmente, die Microsoft Teams Websites zugeordnet](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) sind.

## <a name="background"></a>Hintergrund

Der Haupttreiber für IBs kommt aus der Finanzdienstleistungsbranche. Die Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) überprüft IBs und Interessenkonflikte innerhalb von Mitgliedsunternehmen und bietet Anleitungen zur Bewältigung solcher Konflikte (FINRA 2241, [Debt Research Regulatory Notice 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).

Seit der Einführung von IBs haben sie jedoch in vielen anderen Bereichen als nützlich erachtet. Weitere häufige Szenarien sind:

- **Bildung**: Schüler einer Schule können keine Kontaktdaten für Schüler anderer Schulen nachschlagen.
- **Rechtliches**: Wahrung der Vertraulichkeit von Daten, die vom Anwalt eines Mandanten eingeholt werden, und Verhindern des Zugriffs durch einen Anwalt für dieselbe Firma, die einen anderen Mandanten vertritt.
- **Behörden**: Der Zugriff und die Kontrolle über Informationen sind abteilungs- und gruppenübergreifend beschränkt.
- **Professional Dienstleistungen**: Eine Gruppe von Personen in einem Unternehmen kann während eines Kundenengagements nur mit einem Kunden oder einem bestimmten Kunden über Gastzugriff chatten.

Beispielsweise gehört Enrico zum Segment Banking und Pradeep zum Segment Financial Advisor. Enrico und Pradeep können nicht miteinander kommunizieren, da die IB-Richtlinie der Organisation die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten blockiert. Enrico und Pradeep können jedoch mit Lee im HR kommunizieren.

![Beispiel mit Informationsbarrieren, die die Kommunikation zwischen Segmenten verhindern.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Verwendung von Informationsbarrieren

Möglicherweise möchten Sie IBs in Situationen wie den folgenden verwenden:

- Ein Team muss daran gehindert werden, Daten mit einem bestimmten anderen Team zu kommunizieren oder frei zu geben.
- Ein Team darf keine Daten mit Personen außerhalb des Teams kommunizieren oder freigeben.

Der Evaluierungsdienst für Informationsbarrierenrichtlinien bestimmt, ob eine Kommunikation den IB-Richtlinien entspricht.

## <a name="managing-information-barrier-policies"></a>Verwalten von Richtlinien für Informationsbarrieren

IB-Richtlinien werden im Microsoft Purview-Complianceportal (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](/office365/securitycompliance/information-barriers-policies).

>[!IMPORTANT]
>Bevor Sie Richtlinien einrichten oder definieren, müssen Sie die bereichsbezogene Verzeichnissuche in Microsoft Teams aktivieren. Warten Sie mindestens ein paar Stunden nach dem Aktivieren der bereichsbezogenen Verzeichnissuche, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Administratorrolle für Informationsbarrieren

Die Rolle "IB Compliance Management" ist für die Verwaltung von IB-Richtlinien verantwortlich. Weitere Informationen zu dieser Rolle finden Sie [unter "Berechtigungen" im Microsoft Purview-Complianceportal](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Trigger für Informationsbarrieren

IB-Richtlinien werden aktiviert, wenn die folgenden Teams Ereignisse stattfinden:

- **Mitglieder werden einem Team hinzugefügt**: Wenn Sie einen Benutzer zu einem Team hinzufügen, muss die Richtlinie des Benutzers anhand der IB-Richtlinien anderer Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann der Benutzer alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers verhindert, dass er dem Team hinzugefügt wird, wird der Benutzer nicht in der Suche angezeigt.

    ![Screenshot der Suche nach einem neuen Mitglied, das einem Team hinzugefügt werden soll, und der Suche nach keinen Übereinstimmungen.](media/information-barriers-add-members.png)

- **Ein neuer Chat wird angefordert**: Jedes Mal, wenn ein Benutzer einen neuen Chat mit einem oder mehreren anderen Benutzern anfordert, wird der Chat ausgewertet, um sicherzustellen, dass er keine IB-Richtlinien verletzt. Wenn die Unterhaltung gegen eine IB-Richtlinie verstößt, wird die Unterhaltung nicht gestartet.

    Hier sehen Sie ein Beispiel für einen 1:1-Chat.

    ![Screenshot mit blockierter Kommunikation im 1:1-Chat.](media/information-barriers-one-one-chat.png)

    Hier ist ein Beispiel für einen Gruppenchat.

    ![Screenshot des Gruppenchats.](media/information-barriers-group-chat.png)

- **Ein Benutzer wird zur Teilnahme an einer Besprechung eingeladen**: Wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die ib-Richtlinie, die für den Benutzer gilt, anhand der IB-Richtlinien ausgewertet, die für die anderen Teammitglieder gelten. Wenn ein Verstoß vorliegt, kann der Benutzer nicht an der Besprechung teilnehmen.

    ![Screenshot, der zeigt, dass der Benutzer für die Besprechung gesperrt ist.](media/information-barriers-meeting.png)

- **Ein Bildschirm wird für zwei oder mehr Benutzer freigegeben**: Wenn ein Benutzer einen Bildschirm für andere Benutzer freigibt, muss die Freigabe ausgewertet werden, um sicherzustellen, dass sie nicht gegen die IB-Richtlinien anderer Benutzer verstößt. Wenn eine IB-Richtlinie verletzt wird, ist die Bildschirmfreigabe nicht zulässig.

    Hier ist ein Beispiel für die Bildschirmfreigabe, bevor die Richtlinie angewendet wird.

    ![Screenshot eines Benutzerchats.](media/ib-before-screen-share-policy.png)

    Hier ist ein Beispiel für die Bildschirmfreigabe, nachdem die Richtlinie angewendet wurde. Die Bildschirmfreigabe- und Anrufsymbole sind nicht sichtbar.

    ![Screenshot des Benutzerzeichens mit blockierten Einstellungen.](media/ib-after-screen-share-policy.png)

- **Ein Benutzer platziert einen Telefonanruf in Teams**: Wenn ein Benutzer einen Sprachanruf (über VOIP) an einen anderen Benutzer oder eine Benutzergruppe initiiert, wird der Anruf ausgewertet, um sicherzustellen, dass er nicht gegen die IB-Richtlinien anderer Teammitglieder verstößt. Wenn ein Verstoß vorliegt, wird der Sprachanruf blockiert.

- **Gäste in Teams**: Ib-Richtlinien gelten auch für Gäste in Teams. Wenn Gäste in der globalen Adressliste Ihrer Organisation auffindbar sein müssen, lesen [Sie "Verwalten des Gastzugriffs in Microsoft 365-Gruppen](/microsoft-365/admin/create-groups/manage-guest-access-in-groups)". Sobald Gäste auffindbar sind, können Sie [IB-Richtlinien definieren](/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Auswirkungen von Richtlinienänderungen auf vorhandene Chats

Wenn der IB-Richtlinienadministrator Änderungen an einer Richtlinie vornimmt oder wenn eine Richtlinienänderung aufgrund einer Änderung des Profils eines Benutzers aktiviert wird (z. B. für eine Auftragsänderung), durchsucht der Informationsbarrierenrichtlinienauswertungsdienst automatisch die Mitglieder, um sicherzustellen, dass ihre Mitgliedschaft im Team keine Richtlinien verletzt.

Wenn es einen vorhandenen Chat oder eine andere Kommunikation zwischen Benutzern gibt und eine neue Richtlinie festgelegt oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandene Kommunikationen aus, um sicherzustellen, dass die Kommunikation weiterhin zulässig ist. 

- **1:1-Chat**: Wenn die Kommunikation zwischen zwei Benutzern nicht mehr zulässig ist (aufgrund der Anwendung auf einen oder beide Benutzer einer Richtlinie, die die Kommunikation blockiert), wird die weitere Kommunikation blockiert. Ihre vorhandenen Chatunterhaltungen werden schreibgeschützt.

    Hier ist ein Beispiel, das zeigt, dass der Chat sichtbar ist.

    ![Screenshot, der zeigt, dass der Benutzerchat verfügbar ist.](media/ib-before-1-1chat-policy.png)

    Hier ist ein Beispiel, das zeigt, dass der Chat deaktiviert ist.

    ![Screenshot, der zeigt, dass der Benutzerchat deaktiviert ist.](media/ib-after-1-1chat-policy.png)

- **Gruppenchat**: Wenn die Kommunikation von einem Benutzer zu einer Gruppe nicht mehr zulässig ist (z. B. weil ein Benutzer Aufträge geändert hat), kann der Benutzer – zusammen mit den anderen Benutzern, deren Teilnahme gegen die Richtlinie verstößt – aus dem Gruppenchat entfernt werden, und eine weitere Kommunikation mit der Gruppe ist nicht zulässig. Der Benutzer kann weiterhin alte Unterhaltungen sehen, kann aber keine neuen Unterhaltungen mit der Gruppe sehen oder daran teilnehmen. Wenn die neue oder geänderte Richtlinie, die die Kommunikation verhindert, auf mehrere Benutzer angewendet wird, werden die benutzer, die von der Richtlinie betroffen sind, möglicherweise aus dem Gruppenchat entfernt. Sie können immer noch alte Unterhaltungen sehen.

  In diesem Beispiel wurde Enrico in eine andere Abteilung innerhalb der Organisation verschoben und aus dem Gruppenchat entfernt.

  ![Screenshot eines Gruppenchats, aus dem ein Benutzer entfernt wurde.](media/information-barriers-user-changes-job.png)

  Enrico kann keine Nachrichten mehr an den Gruppenchat senden.

  ![Screenshot: Nachrichten können nicht an Gruppenchat gesendet werden, weil der Benutzer aus der Gruppe entfernt wurde.](media/information-barriers-user-changes-job-2.png)

- **Team**: Alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können keine vorhandenen oder neuen Unterhaltungen sehen oder daran teilnehmen.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Szenario: Ein Benutzer in einem vorhandenen Chat wird blockiert.

Derzeit treten für Benutzer die folgenden Szenarien auf, wenn eine IB-Richtlinie einen anderen Benutzer blockiert:

- **Registerkarte "Personen"**: Ein Benutzer kann blockierte Benutzer auf der Registerkarte " **Personen** " nicht sehen.

- **Personenauswahl**: Blockierte Benutzer werden in der Personenauswahl nicht angezeigt.

    ![Screenshot von Teams, der den Benutzer darauf hinweist, dass die Richtlinie die Anzeige der Informationen eines anderen Benutzers verhindert.](media/information-barriers-people-picker.png)

- **Registerkarte "Aktivität"**: Wenn ein Benutzer die Registerkarte " **Aktivität** " eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf der Registerkarte " **Aktivität** " werden nur Kanalbeiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)

    Hier ist ein Beispiel für die Aktivitätsregisterkartenansicht, die blockiert ist.

    ![Screenshot der aktivitätsregisterkarte, die blockiert ist.](media/ib-after-activity-tab-policy.png)

- **Organigramme**: Wenn ein Benutzer auf ein Organigramm zugreift, in dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer nicht im Organigramm angezeigt. Stattdessen wird eine Fehlermeldung angezeigt.

- **Personenkarte**: Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer später blockiert wird, wird anderen Benutzern eine Fehlermeldung anstelle der Personenkarte angezeigt, wenn sie auf den Namen des blockierten Benutzers zeigen. Auf der Karte aufgelistete Aktionen (z. B. Anrufe und Chats) sind nicht verfügbar.

- **Vorgeschlagene Kontakte**: Blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte (der anfänglichen Kontaktliste, die für neue Benutzer angezeigt wird) angezeigt.

- **Chatkontakte**: Ein Benutzer kann blockierte Benutzer in der Kontaktliste der Chats sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für die blockierten Benutzer ausführen kann, besteht darin, sie zu löschen. Der Benutzer kann den Benutzer auch auswählen, um seine vergangene Unterhaltung anzuzeigen.

- **Anrufkontakte**: Ein Benutzer kann blockierte Benutzer in der Anrufkontaktliste sehen, aber die blockierten Benutzer werden identifiziert. Die einzige Aktion, die der Benutzer für die Blockbenutzer ausführen kann, besteht darin, sie zu löschen.

    Hier ist ein Beispiel für einen blockierten Benutzer in der Anrufkontaktliste.

    > [!div class="mx-imgBorder"]
    > ![Screenshot des Benutzer-Chats.](media/ib-before-chat-contacts-policy.png)

    Hier ist ein Beispiel dafür, wie der Chat für einen Benutzer in der Anrufinhaltsliste deaktiviert wird.

    > [!div class="mx-imgBorder"]
    > ![Screenshot, der zeigt, dass der Benutzer für den Chat gesperrt ist.](media/ib-after-chat-contacts-policy.png)

- **Skype zur Teams Migration**: Während einer Migration von Skype for Business zu Teams werden alle Benutzer – auch die Benutzer, die durch IB-Richtlinien blockiert werden – zu Teams migriert. Diese Benutzer werden dann wie oben beschrieben behandelt.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams von Richtlinien und SharePoint Websites

Wenn ein Team erstellt wird, wird eine SharePoint Website bereitgestellt und Microsoft Teams für die Dateioberfläche zugeordnet. Richtlinien für Informationsbarrieren werden auf dieser SharePoint Website und dateien standardmäßig nicht berücksichtigt. Um Informationsbarrieren in SharePoint und OneDrive zu aktivieren, befolgen Sie die Anleitungen und Schritte im Artikel ["Verwenden von Informationsbarrieren mit SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) Artikel".

## <a name="information--barrier-modes-and-teams"></a>Informationsbarrierenmodi und Teams

Der Modus "Informationsbarrieren" stärkt, wer einem Team hinzugefügt oder daraus entfernt werden kann. Bei der Verwendung von Informationsbarrieren mit Teams werden die folgenden IB-Modi unterstützt:

- **Offen**: Diese Konfiguration ist der Standardmäßige IB-Modus für alle vorhandenen Gruppen, die bereitgestellt wurden, bevor Informationsbarrieren aktiviert wurden. In diesem Modus gelten keine IB-Richtlinien.
- **Implizit**: Diese Konfiguration ist der standardmäßige IB-Modus, wenn ein Team nach dem Aktivieren von Informationsbarrieren bereitgestellt wird. Im impliziten Modus können Sie alle kompatiblen Benutzer in der Gruppe hinzufügen.
- **Besitzer moderiert**: Dieser Modus wird für ein Team festgelegt, wenn Sie die Zusammenarbeit zwischen inkompatiblen Segmentbenutzern zulassen möchten, die vom Besitzer moderiert werden. Der Teambesitzer kann neue Mitglieder gemäß seiner IB-Richtlinie hinzufügen.

Teams, die vor der Aktivierung einer Richtlinie für Informationsbarrieren in Ihrem Mandanten erstellt wurden, werden standardmäßig automatisch auf den *Modus "Öffnen*" festgelegt. Nachdem Sie IB-Richtlinien für Ihren Mandanten aktiviert haben, müssen Sie den Modus Ihrer vorhandenen Teams auf *implizit* aktualisieren, um sicherzustellen, dass vorhandene Teams IB-kompatibel sind.

Verwenden Sie das [Cmdlet Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) mit dem *Parameter "InformationBarrierMode* ", der dem Modus entspricht, den Sie für Ihre Segmente verwenden möchten. Zulässige Werteliste für den *Parameter "InformationBarrierMode* " sind *"Open*", *"Implicit*" und *"Owner Moderated*".

Um beispielsweise den *impliziten* Modus für eine Microsoft 365 Gruppe zu konfigurieren, verwenden Sie den folgenden PowerShell-Befehl:

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

Verwenden Sie dieses [PowerShell-Skript](information-barriers-mode-script.md), um den Modus von "Öffnen" auf "Implizit" für alle vorhandenen Teams zu aktualisieren.

Wenn Sie die Konfiguration des Modus "Öffnen" für vorhandene Teams-verbundenen Gruppen ändern, um die Complianceanforderungen für Ihre Organisation zu erfüllen, müssen Sie [die IB-Modi](/sharepoint/information-barriers#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell) für zugeordnete SharePoint Websites aktualisieren, die mit dem Teams Team verbunden sind.

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Weitere Informationen zu Lizenzen und Berechtigungen, Plänen und Preisen finden Sie [unter Microsoft 365 Lizenzierungsleitfaden für Sicherheit & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="known-issues"></a>Bekannte Probleme

- **Benutzer können nicht an Ad-hoc-Besprechungen teilnehmen: Wenn IB-Richtlinien** aktiviert sind, können Benutzer nicht an Besprechungen teilnehmen, wenn die Größe der Besprechungsliste größer als die [Anwesenheitsbeschränkungen für Besprechungen](limits-specifications-teams.md) ist. Die Ursache dafür ist, dass IB-Prüfungen davon abhängen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können, und nur wenn sie der Teilnehmerliste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Ein Benutzer, der einmal an einer Besprechung teiltritt, fügt diesen Benutzer der Teilnehmerliste hinzu. Daher kann sich die Teilnehmerliste bei Besprechungsserien schnell füllen. Sobald die Chatliste die [Anwesenheitsbeschränkungen für Besprechungen](limits-specifications-teams.md) erreicht hat, können der Besprechung keine weiteren Benutzer hinzugefügt werden. Wenn IB für die Organisation aktiviert ist und die Chatliste für eine Besprechung voll ist, dürfen neue Benutzer (benutzer, die noch nicht in der Liste sind) nicht an der Besprechung teilnehmen. Wenn IB jedoch nicht für die Organisation aktiviert ist und die Besprechungschatliste voll ist, können neue Benutzer (die Benutzer, die noch nicht in der Liste sind) an der Besprechung teilnehmen, obwohl die Chatoption in der Besprechung nicht angezeigt wird. Eine kurzfristige Lösung besteht darin, inaktive Mitglieder aus der Besprechungschatliste zu entfernen, um Platz für neue Benutzer zu schaffen. Wir werden jedoch die Größe der Teilnehmerlisten für Besprechungschats zu einem späteren Zeitpunkt erhöhen.
- **Benutzer können nicht an Kanalbesprechungen teilnehmen**: Wenn IB-Richtlinien aktiviert sind, können Benutzer nicht an Kanalbesprechungen teilnehmen, wenn sie kein Mitglied des Teams sind. Die Ursache dafür ist, dass IB-Prüfungen davon abhängen, ob Benutzer einer Besprechungschatliste hinzugefügt werden können, und nur wenn sie der Teilnehmerliste hinzugefügt werden können, dürfen sie an der Besprechung teilnehmen. Der Chatthread in einer Kanalbesprechung ist nur für Team-/Kanalmitglieder verfügbar, und Nichtmitglieder können den Chatthread nicht sehen oder darauf zugreifen. Wenn IB für die Organisation aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teilzunehmen, darf dieser Benutzer nicht an der Besprechung teilnehmen. Wenn IB jedoch nicht* für die Organisation aktiviert ist und ein Nicht-Teammitglied versucht, an einer Kanalbesprechung teilzunehmen, ist der Benutzer berechtigt, an der Besprechung teilzunehmen, aber die Chatoption wird in der Besprechung nicht angezeigt.
- **Maximale Anzahl zulässiger Segmente in einer Organisation**: Jede Organisation kann bis zu 100 Segmente beim Konfigurieren von IB-Richtlinien einrichten. Es gibt keine Beschränkung für die Anzahl der Richtlinien, die konfiguriert werden können.
- **IB-Richtlinien funktionieren nicht für Verbundbenutzer**: Wenn Sie den Partnerverbund mit externen Organisationen zulassen, werden die Benutzer dieser Organisationen nicht durch IB-Richtlinien eingeschränkt. Wenn Benutzer Ihrer Organisation an einem Chat oder einer Besprechung teilnehmen, die von externen Verbundbenutzern organisiert wird, schränken IB-Richtlinien auch die Kommunikation zwischen Benutzern Ihrer Organisation nicht ein.

## <a name="more-information"></a>Weitere Informationen

- Weitere Informationen zu IBs finden Sie unter [Informationsbarrieren](/office365/securitycompliance/information-barriers).
- Informationen zum Einrichten von IB-Richtlinien finden Sie [unter Erste Schritte mit Informationsbarrieren](/office365/securitycompliance/information-barriers-policies).
- Informationen zum Bearbeiten oder Entfernen von IB-Richtlinien finden [Sie unter Verwalten von Richtlinien für Informationsbarrieren](/microsoft-365/compliance/information-barriers-edit-segments-policies).
- [Informationsbarrieren und freigegebene Kanäle](information-barriers-shared-channels.md)

## <a name="availability"></a>Verfügbarkeit

Informationsbarrieren in Teams sind in unseren öffentlichen, GCC, GCC - High- und DOD-Clouds verfügbar.
