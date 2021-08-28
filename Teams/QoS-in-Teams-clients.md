---
title: Implementieren von Quality of Service (QoS) in Microsoft Teams Clients
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie Sie Quality of Service (QoS) verwenden, um den Netzwerkdatenverkehr für den Microsoft Teams-Client zu optimieren.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: c283a66db274bc8723d429631bf265fdb0f5206b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606014"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams Clients

Sie können richtlinienbasierte Quality of Service (QoS) innerhalb einer Gruppenrichtlinie verwenden, um den Quellportbereich für den vordefinierten DSCP-Wert im Client für Teams festlegen. Die Portbereiche, die in der folgenden Tabelle angegeben sind, sind ein Ausgangspunkt zum Erstellen einer Richtlinie für jede Arbeitsauslastung.

*Tabelle 1. Empfohlene anfängliche Portierungsbereiche*

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Konfigurieren Sie nach Möglichkeit richtlinienbasierte QoS-Einstellungen innerhalb eines Gruppenrichtlinienobjekts. Die folgenden Schritte sind mit dem Konfigurieren von [Portbereichen](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)und einer Quality of Service-Richtlinie für Ihre Clients auf Skype for Business Server vergleichbar, die einige zusätzliche Details enthält, die möglicherweise nicht erforderlich sind.

Um eine QoS-Audiorichtlinie für Domänen bei Windows 10-Computern zu erstellen, melden Sie sich zuerst an einem Computer an, auf dem die Gruppenrichtlinienverwaltung installiert wurde. Öffnen Sie die Gruppenrichtlinienverwaltung (klicken Sie auf Start, zeigen Sie auf Verwaltungstools, und klicken Sie dann auf Gruppenrichtlinienverwaltung), und führen Sie dann die folgenden Schritte aus:

1. Suchen Sie in "Gruppenrichtlinienverwaltung" den Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Clientcomputer in einer Organisationseinheit namens Clients **befinden,** sollte die neue Richtlinie in der Clients-OU erstellt werden.

1. Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf Gruppenrichtlinienobjekt in dieser Domäne erstellen **und dann auf Hier verknüpfen.**

1. Geben Sie **im Dialogfeld Neues Gruppenrichtlinienobjekt** im Feld **Name** einen Namen für das neue Gruppenrichtlinienobjekt ein, und klicken Sie dann auf **OK.**

1. Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann **auf Bearbeiten**.

1. Erweitern Sie im Gruppenrichtlinienverwaltungs-Editor computerkonfiguration **,** erweitern Sie **Windows Einstellungen**, klicken Sie mit der rechten Maustaste auf Richtlinienbasiertes **QoS,** und klicken Sie dann auf **Neue Richtlinie erstellen**.

1. Geben Sie **im Dialogfeld Richtlinienbasiertes QoS** auf der Ersten Seite im Feld Name einen Namen für die neue **Richtlinie** ein. Wählen **Sie DSCP-Wert angeben aus,** und legen Sie den Wert auf **46 fest.** Lassen **Sie Die ausgehende Drosselungsrate** angeben deaktiviert, und klicken Sie dann auf **Weiter.**

1. Wählen Sie auf  der nächsten Seite Nur Anwendungen mit diesem ausführbaren Namen aus, geben Sie den NamenTeams.exe **ein,** und klicken Sie dann auf **Weiter.** Mit dieser Einstellung wird die Richtlinie angewiesen, nur übereinstimmenden Datenverkehr vom Client zu Teams priorisieren.

1. Stellen Sie auf der dritten Seite sicher, dass sowohl **Quell-IP-Adresse** als auch **Ziel-IP-Adresse** ausgewählt sind, und klicken Sie dann auf **Weiter.** Diese beiden Einstellungen stellen sicher, dass Pakete unabhängig davon verwaltet werden, von welchem Computer (der IP-Adresse) die Pakete gesendet wurden und von welchem Computer (der IP-Adresse) die Pakete empfangen werden.

1. Wählen Sie auf Seite 4 in der Dropdownliste Das Protokoll **auswählen, das diese QoS-Richtlinie** gilt für TCP und **UDP** aus. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden Netzwerkprotokolle, die am häufigsten verwendet werden.

1. Wählen Sie unter der **Überschrift Geben Sie die Quellportnummer an** die Option Von diesem **Quellport oder -bereich aus.** Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie z. B. die Ports 50000 bis Ports 50019 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in diesem Format ein: **50000:50019.** Klicken Sie auf **Fertig stellen**.

1. Wiederholen Sie die Schritte 5 bis 10, um Richtlinien für Video und Anwendungs-/Desktopfreigabe zu erstellen und die entsprechenden Werte in Schritt 6 und 10 zu ersetzen.

Die von Ihnen erstellten neuen Richtlinien werden erst wirksam, wenn die Gruppenrichtlinie auf den Clientcomputern aktualisiert wurde. Obwohl Gruppenrichtlinien automatisch automatisch aktualisiert werden, können Sie eine sofortige Aktualisierung erzwingen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie auf jedem Computer, für den Sie die Gruppenrichtlinie aktualisieren möchten, eine Eingabeaufforderung als Administrator *(Als Administrator ausführen).*

1. Geben Sie an der Eingabeaufforderung

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Überprüfen von DSCP-Markierungen im Gruppenrichtlinienobjekt

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Werte aus dem Gruppenrichtlinienobjekt festgelegt wurden:

1. Öffnen Sie eine Eingabeaufforderung als Administrator *(Als Administrator ausführen).*

1. Geben Sie an der Eingabeaufforderung

   ```console
   gpresult /R > gp.txt
   ```

   Dadurch wird ein Bericht der angewendeten Gruppenrichtlinienobjekte generiert und an eine Textdatei namens *gp.txt.*

   Geben Sie für einen besser lesbaren HTML-Bericht *gp.html* den folgenden Befehl ein:

   ```console
   gpresult /H gp.html
   ```

1. Suchen Sie in der generierten Datei nach der Überschrift Angewendete Gruppenrichtlinienobjekte, und vergewissern Sie sich, dass die Namen der zuvor erstellten Gruppenrichtlinienobjekte in der Liste der angewendeten Richtlinien enthalten sind. 

1. Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu

   HKEY \_ LOCAL MACHINE Software Policies Microsoft Windows \_ \\ \\ \\ \\ \\ QoS

   Überprüfen Sie die Werte für die Registrierungseinträge, die in Tabelle 2 aufgeführt sind.

   *Tabelle 2. Werte für Windows Registrierungseinträge für QoS*

   |          Name          |  Typ  |    Daten     |
   |         :---:          | :---:  |    :---:    |
   |    Application Name    | REG_SZ |  Teams.exe  |
   |       DSCP Value       | REG_SZ |     46      |
   |        Local IP        | REG_SZ |     \*      |
   | Local IP Prefix Length | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        Protokoll        | REG_SZ |     \*      |
   |       Remote IP        | REG_SZ |     \*      |
   |    Remote-IP-Präfix    | REG_SZ |     \*      |
   |      Remote Port       | REG_SZ |     \*      |
   |     Throttle Rate      | REG_SZ |     -1      |
   | | | |

1. Überprüfen Sie, ob der Wert für den Eintrag Anwendungsname für den von Ihnen verwendeten Client korrekt ist, und vergewissern Sie sich, dass sowohl die DSCP-Wert- als auch die Einträge für den lokalen Port die Einstellungen im Gruppenrichtlinienobjekt widerspiegeln.


## <a name="related-topics"></a>Verwandte Themen

[Implementieren von Quality of Service (QoS) in Teams](QoS-in-Teams.md)