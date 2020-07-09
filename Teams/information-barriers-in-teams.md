---
title: Informationsbarrieren in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: In diesem Artikel wird erläutert, was Informationsbarrieren in Microsoft Teams sind und wie Sie sich auf Teams auswirken.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce71f0c0f2621253698cd250372624ded638dcec
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083185"
---
# <a name="information-barriers-in-microsoft-teams"></a>Informationsbarrieren in Microsoft Teams

Informationsbarrieren (IB) sind Richtlinien, die ein Administrator konfigurieren kann, um zu verhindern, dass Einzelpersonen oder Gruppen miteinander kommunizieren. Dies ist hilfreich, wenn beispielsweise eine Abteilung Informationen verarbeitet, die nicht für andere Abteilungen freigegeben werden sollen, oder eine Gruppe verhindert oder isoliert werden muss, um mit Personen außerhalb dieser Gruppe zu kommunizieren.

> [!NOTE]
> - Gruppen für Informationsbarrieren können nicht für Mandanten erstellt werden.
> - Die Verwendung von Bots zum Hinzufügen von Benutzern wird in Version 1 nicht unterstützt.
> - Private Kanäle sind mit Richtlinien für Informationsbarrieren kompatibel, die Sie konfigurieren.
> - Neu: Informations Barriere-Unterstützung für SharePoint-Websites, die mit Teams verbunden sind, befindet sich jetzt in privater Vorschau. Klicken Sie [hier](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) , um an der privaten Vorschau teilzunehmen.

Richtlinien für Informationsbarrieren verhindern auch Nachschlagevorgänge und Ermittlungen. Wenn Sie versuchen, mit einer Person zu kommunizieren, mit der Sie nicht kommunizieren sollten, wird dieser Benutzer in der Personenauswahl nicht gefunden.

## <a name="background"></a>Hintergrund

Der wichtigste Treiber für Informationsbarrieren ist die Finanzdienstleistungsbranche. Die Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) überprüft Informationsbarrieren und Interessenkonflikte innerhalb von Mitgliedsunternehmen und bietet Anleitungen für die Verwaltung solcher Konflikte (FINRA 2241, [Debt Research Regulation Notice 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

Da jedoch Informationsbarrieren eingeführt wurden, haben viele andere Bereiche Sie als nützlich erwiesen. Weitere häufige Szenarien sind:

- Bildung: Schüler in einer Schule können keine Kontaktinformationen für Schüler anderer Schulen nachschlagen.
- Legal: Wahrung der Vertraulichkeit der Daten, die der Rechtsanwalt eines Mandanten erhalten hat, um von einem Rechtsanwalt für das gleiche Unternehmen, das einen anderen Mandanten darstellt, zugegriffen zu werden.
- Regierung: Informationszugriff und-Steuerung sind über Abteilungen und Gruppen hinweg limitiert.
- Professionelle Dienstleistungen: eine Gruppe von Personen in einem Unternehmen kann während eines Kundenengagements nur über Föderations-oder Gastzugriff mit einem Kunden oder bestimmten Kunden chatten.

Zum Beispiel gehört Enrico zum Segment Banking, und Pradeep gehört zum Segment Financial Advisor. Enrico und Pradeep können nicht miteinander kommunizieren, weil die IB-Richtlinie der Organisation die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten blockiert. Allerdings können Enrico und Pradeep mit Lee in HR kommunizieren.

![Beispiel mit Informationsbarrieren, die die Kommunikation zwischen Segmenten verhindern](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Verwendung von Informationsbarrieren

Möglicherweise möchten Sie Informationsbarrieren in Situationen wie den folgenden verwenden:

- Ein Team muss daran gehindert werden, Daten mit einem bestimmten anderen Team zu kommunizieren oder zu teilen.
- Ein Team darf keine Daten an Personen außerhalb des Teams weitergeben oder freigeben.

Der Evaluierungs Dienst für Informations Barriere-Richtlinien bestimmt, ob eine Kommunikation den Richtlinien für Informationsbarrieren entspricht.

## <a name="managing-information-barrier-policies"></a>Verwalten von Richtlinien für Informationsbarrieren

Richtlinien für Informationsbarrieren werden im Microsoft 365 Compliance Center (SCC) mithilfe von PowerShell-Cmdlets verwaltet. Weitere Informationen finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Bevor Sie Richtlinien einrichten oder definieren, **müssen Sie die Bereichs Verzeichnissuche in Microsoft Teams aktivieren**. Warten Sie mindestens ein paar Stunden nach der Aktivierung der Bereichs Verzeichnissuche, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren. [Informieren Sie sich über die Voraussetzungen für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Administratorrolle für Informationsbarrieren

Die IB-Compliance-Verwaltungsrolle ist für die Verwaltung von Richtlinien für Informationsbarrieren verantwortlich. Weitere Informationen zu dieser Rolle finden Sie unter [Berechtigungen im Microsoft 365 Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Trigger für Informations Barriere

Richtlinien für Informationsbarrieren werden aktiviert, wenn die folgenden Teams-Ereignisse stattfinden:

- **Mitglieder werden einem Team hinzugefügt** – Wenn Sie einen Benutzer zu einem Team hinzufügen, muss die Richtlinie des Benutzers mit den Richtlinien für Informationsbarrieren anderer Teammitglieder ausgewertet werden. Nachdem der Benutzer erfolgreich hinzugefügt wurde, kann der Benutzer alle Funktionen im Team ohne weitere Überprüfungen ausführen. Wenn die Richtlinie des Benutzers blockiert, dass Sie dem Team hinzugefügt wird, wird der Benutzer nicht in der Suche angezeigt.

    ![Screenshot mit Gruppen-Chat](media/information-barriers-add-members.png)

- **Ein neuer Chat wird angefordert** – jedes Mal, wenn ein neuer Chat zwischen zwei oder mehr Benutzern angefordert wird, wird der Chat ausgewertet, um sicherzustellen, dass er keine Richtlinien für Informationsbarrieren verletzt. Wenn die Unterhaltung gegen eine Richtlinie für Informationsbarrieren verstößt, wird die Unterhaltung nicht initiiert.

    Hier ist ein Beispiel für einen 1:1-Chat.

     ![Screenshot mit blockierter Kommunikation in 1:1-Chat](media/information-barriers-one-one-chat.png)

    Hier ist ein Beispiel für einen Gruppen-Chat.

    ![Screenshot mit Gruppen-Chat](media/information-barriers-group-chat.png)

- **Ein Benutzer ist eingeladen, an einer Besprechung teilzunehmen** – wenn ein Benutzer zur Teilnahme an einer Besprechung eingeladen wird, wird die Richtlinie des Benutzers anhand der Richtlinien anderer Teammitglieder ausgewertet, und wenn ein Verstoß vorliegt, ist der Benutzer nicht berechtigt, an der Besprechung teilzunehmen.

    ![Screenshot des Benutzers, der von einer Besprechung blockiert wurde](media/information-barriers-meeting.png)

- **Ein Bildschirm wird von zwei oder mehr Benutzern freigegeben** – jedes Mal, wenn ein Bildschirm von zwei oder mehr Benutzern freigegeben wird, muss die Bildschirmfreigabe ausgewertet werden, um sicherzustellen, dass Sie die Richtlinien anderer Benutzer für Informationsbarrieren nicht verletzt. Wenn eine Richtlinie für Informationsbarrieren verletzt wird, ist die Bildschirmfreigabe nicht zulässig. 
 
    Hier ist ein Beispiel für die Bildschirmfreigabe, bevor die Richtlinie angewendet wird. 

    ![Screenshot mit einem Benutzer-Chat](media/ib-before-screen-share-policy.png)

    Nachfolgend finden Sie ein Beispiel für die Bildschirmfreigabe, nachdem die Richtlinie angewendet wurde. Bildschirmfreigabe-und Anruf Symbole werden nicht angezeigt.

    ![Screenshot mit Benutzer-char mit blockierten Einstellungen](media/ib-after-screen-share-policy.png)

- **Ein Benutzer platziert einen Telefonanruf (VoIP) in Teams** – wenn ein Sprachanruf von einem Benutzer an einen anderen Benutzer oder eine Gruppe von Benutzern initiiert wird, wird der Anruf ausgewertet, um sicherzustellen, dass er die Richtlinien anderer Teammitglieder gegen die Informations Barriere nicht verletzt. Bei Verstößen ist der Sprachanruf blockiert.
- **Gastbenutzer in Teams** – Richtlinien für Informationsbarrieren gelten auch für Gastbenutzer in Teams. Wenn Gastbenutzer in der globalen Adressliste Ihrer Organisation auffindbar sein müssen, lesen Sie Verwalten des [Gastzugriffs in Microsoft 365-Gruppen](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Sobald Gastbenutzer auffindbar sind, können Sie [Richtlinien für Informationsbarrieren definieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Auswirkungen von Richtlinienänderungen auf vorhandene Chats

Wenn der Administrator der Informations Barriere-Richtlinie Änderungen an einer Richtlinie vornimmt oder eine Richtlinienänderung aufgrund einer Änderung des Profils eines Benutzers (beispielsweise bei einer Auftragsänderung oder einem ähnlichen Grund) in Kraft tritt, durchsucht der Evaluierungs Dienst der Informations Barriere-Richtlinie automatisch die Mitglieder, um sicherzustellen, dass die Mitglieder des Teams keine Richtlinien verletzen.

Wenn ein Chat oder eine andere Kommunikation zwischen Benutzern vorhanden ist, eine neue Richtlinie festgesetzt oder eine vorhandene Richtlinie geändert wird, wertet der Dienst vorhandene Kommunikation aus, um sicherzustellen, dass die Kommunikation weiterhin zulässig ist. 

- **1:1-Chat** – wenn die Kommunikation zwischen den beiden Benutzern nicht mehr zulässig ist (wenn eine Richtlinie, die die Kommunikation blockiert, auf einen oder beide Benutzer angewendet wird), wird die weitere Kommunikation blockiert, und die Chat Unterhaltung wird schreibgeschützt. 

    Hier ist ein Beispiel, das zeigt, dass der Chat sichtbar ist.

    ![Screenshot mit Benutzer-Chat verfügbar](media/ib-before-1-1chat-policy.png)

    Hier ist ein Beispiel, das zeigt, dass der Chat deaktiviert ist.

    ![Screenshot, der zeigt, dass der Benutzer Chat deaktiviert ist](media/ib-after-1-1chat-policy.png)

- **Gruppen-Chat** – wenn die Kommunikation von einem Benutzer zur Gruppe nicht mehr zulässig ist (Wenn beispielsweise ein Benutzer die Arbeit wechselt), kann der Benutzer zusammen mit den anderen Benutzern, die gegen die Richtlinie verstoßen, aus dem Gruppen-Chat entfernt werden, und die weitere Kommunikation mit der Gruppe ist nicht zulässig. Der Benutzer kann weiterhin alte Konversationen sehen (die schreibgeschützt sind), aber nicht in der Lage sein, neue Konversationen mit der Gruppe zu sehen oder daran teilzunehmen. Wenn die neue oder geänderte Richtlinie, die die Kommunikation verhindert, auf mehr als einen Benutzer angewendet wird, werden die Benutzer, die von der Richtlinie betroffen sind, möglicherweise aus dem Gruppen-Chat entfernt. Sie können weiterhin alte Konversationen sehen.

In diesem Beispiel zog Enrico zu einer anderen Abteilung innerhalb der Organisation und wird aus dem Gruppen-Chat entfernt.

  ![Screenshot mit Gruppen-Chat](media/information-barriers-user-changes-job.png)

Enrico kann keine Nachrichten mehr an den Gruppen-Chat senden.

  ![Screenshot mit Gruppen-Chat](media/information-barriers-user-changes-job-2.png)

- **Team** – alle Benutzer, die aus der Gruppe entfernt wurden, werden aus dem Team entfernt und können keine vorhandenen oder neuen Konversationen anzeigen oder daran teilnehmen.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Szenario: ein Benutzer in einem vorhandenen Chat wird blockiert

Derzeit erfahren Benutzer Folgendes, wenn eine Richtlinie für Informationsbarrieren einen anderen Benutzer blockiert:

- **Registerkarte "Personen"** – Benutzer können auf der Registerkarte **Personen** keine blockierten Benutzer sehen.
- **Personenauswahl** – blockierte Benutzer werden in der Personenauswahl nicht angezeigt.

    ![Screenshot mit Gruppen-Chat](media/information-barriers-people-picker.png)
    
- **Registerkarte "Aktivität"** – wenn ein Benutzer die Registerkarte " **Aktivität** " eines blockierten Benutzers besucht, werden keine Beiträge angezeigt. (Auf der Registerkarte **Aktivität** werden nur Kanal Beiträge angezeigt, und es gibt keine gemeinsamen Kanäle zwischen den beiden Benutzern.)

    Hier sehen Sie ein Beispiel für die blockierte Aktivitäts Registerkartenansicht.

    ![Screenshot der blockierten Aktivitäten-Registerkarte](media/ib-after-activity-tab-policy.png)


- **Organigramme** : Wenn ein Benutzer auf ein Organigramm zugreift, auf dem ein blockierter Benutzer angezeigt wird, wird der blockierte Benutzer im Organigramm nicht angezeigt, und stattdessen wird eine Fehlermeldung angezeigt.
- **Personen Karte** : Wenn ein Benutzer an einer Unterhaltung teilnimmt und der Benutzer anschließend blockiert wird, werden anderen Benutzern anstelle der Personen Karte eine Fehlermeldung angezeigt, wenn Sie den Mauszeiger über den Namen des blockierten Benutzers bewegen. Auf der Karte aufgelistete Aktionen (wie Anrufe und Chats) sind nicht verfügbar.
- **Vorgeschlagene Kontakte** – blockierte Benutzer werden nicht in der Liste der vorgeschlagenen Kontakte angezeigt (die erste Kontaktliste, die für neue Benutzer angezeigt wird).
- **Chat-Kontakte** : ein Benutzer kann blockierte Benutzer in der Chat-Kontaktliste sehen, die blockierten Benutzer werden jedoch identifiziert, und die einzige Aktion, die der Benutzer ausführen kann, besteht darin, diese zu löschen. Der Benutzer kann auch darauf klicken, um seine frühere Konversation anzuzeigen.
- **Anrufe an Kontakte** : ein Benutzer kann blockierte Benutzer in der Anruf Kontaktliste sehen, die blockierten Benutzer werden jedoch identifiziert, und die einzige Aktion, die der Benutzer ausführen kann, besteht darin, diese zu löschen.

    Hier ist ein Beispiel für einen blockierten Benutzer in der Kontaktliste "Anrufe".

    ![Screenshot mit Benutzer-Chat](media/ib-before-chat-contacts-policy.png)

    Im folgenden finden Sie ein Beispiel für die Deaktivierung des Chats für einen Benutzer in der Liste der Anruf Inhalte.

    ![Screenshot des Benutzers, der im Chat blockiert ist](media/ib-after-chat-contacts-policy.png)

- **Migration von Skype zu Teams** – während einer Migration von Skype for Business zu Teams werden alle Benutzer, auch solche, die durch Richtlinien für Informationsbarrieren blockiert sind, in Teams migriert und dann wie oben beschrieben gehandhabt.

## <a name="teams-policies-and-sharepoint-sites"></a>Teamrichtlinien und SharePoint-Websites

Wenn ein Team erstellt wird, wird eine SharePoint-Website bereitgestellt und dem Team für die Datei Oberfläche zugeordnet. Der Zugriff auf diese SharePoint-Website und Dateien honoriert die IB der Organisation, das heißt, nur die Benutzer, deren IB-Segment Übereinstimmungen pro IB-Richtlinie haben, können den Zugriff gewähren. Auch zum Zeitpunkt der Dateifreigabe wird die IB-Richtlinie berücksichtigt.

Beispiel: in der Contoso Bank Corporation gehört der Benutzer "Sesha@contosobank.onmicrosoft.com" zum Segment Investment Banking, und der Benutzer "Nikita@contosobank.onmicrosoft.com" gehört zur Segment Beratung. Die IB-Richtlinie der Organisation blockiert die Kommunikation und Zusammenarbeit zwischen diesen beiden Segmenten.
Wenn der Benutzer Sesha ein Team für das Segment Investment Banking erstellt, sind das Team und die SharePoint-Website, die es zurückgibt, nur für Benutzer des Segments Investment Banking zugänglich. Benutzer Nikita kann nicht auf diese Website zugreifen, selbst wenn Sie über die Website Verknüpfung verfügt.

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Weitere Informationen, einschließlich Pläne und Preise, finden Sie unter [Lizenzierungs Leit Faden](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="more-information"></a>Weitere Informationen

- Wenn Sie mehr über Informationsbarrieren erfahren möchten, lesen Sie [Informationen zu Barrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Informationen zum Einrichten von Richtlinien für Informationsbarrieren finden Sie unter [Definieren von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Informationen zum Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren finden Sie unter [Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).
