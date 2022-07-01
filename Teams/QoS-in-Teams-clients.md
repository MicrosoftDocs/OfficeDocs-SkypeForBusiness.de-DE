---
title: Implementieren von Quality of Service (QoS) in Microsoft Teams-Clients
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Erfahren Sie, wie Sie QoS (Quality of Service) verwenden, um den Netzwerkdatenverkehr für den Microsoft Teams-Desktopclient zu optimieren.
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
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563923"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementieren von Quality of Service (QoS) in Microsoft Teams-Clients

Sie können richtlinienbasierte Quality of Service (QoS) innerhalb Gruppenrichtlinie verwenden, um den Quellportbereich für den vordefinierten DSCP-Wert im Teams-Client festzulegen. Die in der folgenden Tabelle angegebenen Portbereiche sind ein Ausgangspunkt zum Erstellen einer Richtlinie für jede Workload.

*Tabelle 1. Empfohlene anfängliche Portbereiche*

|Typ des Mediendatenverkehrs| Client-Quellportbereich  |Protokoll|DSCP-Wert|DSCP-Klasse|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Anwendung/Bildschirmfreigabe| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Konfigurieren Sie nach Möglichkeit richtlinienbasierte QoS-Einstellungen innerhalb eines Gruppenrichtlinie-Objekts. Die folgenden Schritte ähneln dem [Konfigurieren von Portbereichen und einer Quality of Service-Richtlinie für Ihre Clients auf Skype for Business Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), die einige zusätzliche Details enthält, die möglicherweise nicht erforderlich sind.

Um eine QoS-Audiorichtlinie für in die Domäne eingebundene Windows 10 Computer zu erstellen, melden Sie sich zuerst bei einem Computer an, auf dem Gruppenrichtlinie Management installiert wurde. Öffnen Sie Gruppenrichtlinie Verwaltung (klicken Sie auf "Start", zeigen Sie auf "Verwaltungstools", und klicken Sie dann auf Gruppenrichtlinie Verwaltung), und führen Sie dann die folgenden Schritte aus:

1. Suchen Sie in Gruppenrichtlinie Verwaltung den Container, in dem die neue Richtlinie erstellt werden soll. Wenn sich beispielsweise alle Ihre Clientcomputer in einer OE mit dem Namen **"Clients**" befinden, sollte die neue Richtlinie in der Clients-OE erstellt werden.

1. Klicken Sie mit der rechten Maustaste auf den entsprechenden Container, und klicken Sie dann auf **"Gruppenrichtlinienobjekt in dieser Domäne erstellen", und verknüpfen Sie es hier**.

1. Geben Sie im Dialogfeld **"Neues Gruppenrichtlinienobjekt**" im Feld "**Name**" einen Namen für das neue Gruppenrichtlinie-Objekt ein, und klicken Sie dann auf **"OK**".

1. Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und klicken Sie dann auf **"Bearbeiten"**.

1. Erweitern Sie im Gruppenrichtlinie-Verwaltungs-Editor die **Option "Computerkonfiguration**", erweitern **Sie die Windows-Einstellungen**, klicken Sie mit der rechten Maustaste auf **richtlinienbasiertes QoS**, und klicken Sie dann auf **"Neue Richtlinie erstellen**".

1. Geben Sie im Dialogfeld **"Richtlinienbasiertes QoS** " auf der öffnenden Seite im Feld " **Name** " einen Namen für die neue Richtlinie ein. Wählen Sie **"DSCP-Wert angeben** " aus, und legen Sie den Wert auf **46** fest. Lassen **Sie "Ausgehende Drosselungsrate angeben** " deaktiviert, und klicken Sie dann auf **"Weiter**".

1. Wählen Sie auf der nächsten Seite **"Nur Anwendungen mit diesem ausführbaren Namen** " aus, geben Sie den Namen **Teams.exe** ein, und klicken Sie dann auf **"Weiter**". Diese Einstellung weist die Richtlinie an, nur übereinstimmenden Datenverkehr vom Teams-Client zu priorisieren.

1. Stellen Sie auf der dritten Seite sicher, dass sowohl **"Beliebige Quell-IP-Adresse** " als auch " **Beliebige Ziel-IP-Adresse** " ausgewählt sind, und klicken Sie dann auf **"Weiter**". Diese beiden Einstellungen stellen sicher, dass Pakete verwaltet werden, unabhängig davon, welcher Computer (IP-Adresse) die Pakete gesendet hat und welcher Computer (IP-Adresse) die Pakete empfängt.

1. Wählen Sie auf Seite 4 **TCP und UDP** aus dem **Protokoll aus, das diese QoS-Richtlinie für die** Dropdownliste anwendet. TCP (Transmission Control Protocol) und UDP (User Datagram Protocol) sind die beiden am häufigsten verwendeten Netzwerkprotokolle.

1. Wählen Sie unter der Überschrift **"Quellportnummer angeben**" **die Option "Von diesem Quellport oder Bereich" aus**. Geben Sie im zugehörigen Textfeld den Portbereich ein, der für Audioübertragungen reserviert ist. Wenn Sie beispielsweise die Ports 50000 bis 50019 für Audiodatenverkehr reserviert haben, geben Sie den Portbereich in folgendem Format ein: **50000:50019**. Klicken Sie auf **Fertig stellen**.

1. Wiederholen Sie die Schritte 5 bis 10, um Richtlinien für die Video- und Anwendungs-/Desktopfreigabe zu erstellen und dabei die entsprechenden Werte in schritt 6 und 10 zu ersetzen.

Die von Ihnen erstellten neuen Richtlinien werden erst wirksam, wenn Gruppenrichtlinie auf Ihren Clientcomputern aktualisiert wurde. Obwohl Gruppenrichtlinie regelmäßig von selbst aktualisiert wird, können Sie eine sofortige Aktualisierung erzwingen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie auf jedem Computer, für den Sie Gruppenrichtlinie aktualisieren möchten, eine Eingabeaufforderung als Administrator (*Als Administrator ausführen*).

1. Geben Sie an der Eingabeaufforderung

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Überprüfen der DSCP-Markierungen im Gruppenrichtlinie-Objekt

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Werte aus dem Gruppenrichtlinie Objekt festgelegt wurden:

1. Öffnen Sie eine Eingabeaufforderung als Administrator (*Als Administrator ausführen*).

1. Geben Sie an der Eingabeaufforderung

   ```console
   gpresult /R > gp.txt
   ```

   Dadurch wird ein Bericht der angewendeten GRUPPENrichtlinienobjekte generiert und an eine Textdatei namens *gp.txt* gesendet.

   Geben Sie für einen besser lesbaren HTML-Bericht namens *gp.html* den folgenden Befehl ein:

   ```console
   gpresult /H gp.html
   ```

1. Suchen Sie in der generierten Datei nach der Überschrift **"Angewendete Gruppenrichtlinie Objekte**", und überprüfen Sie, ob sich die Namen der zuvor erstellten Gruppenrichtlinie Objekte in der Liste der angewendeten Richtlinien befinden.

1. Öffnen Sie den Registrierungs-Editor, und wechseln Sie zu

   HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS

   Überprüfen Sie die Werte für die in Tabelle 2 aufgeführten Registrierungseinträge.

   *Tabelle 2. Werte für Windows-Registrierungseinträge für QoS*

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

1. Überprüfen Sie, ob der Wert für den Anwendungsnameneintrag für den von Ihnen verwendeten Client korrekt ist, und stellen Sie sicher, dass sowohl der DSCP-Wert als auch die Einträge für den lokalen Port die Einstellungen im Gruppenrichtlinie-Objekts widerspiegeln.


## <a name="related-topics"></a>Verwandte Themen

[Implementieren von Quality of Service (QoS) in Teams](QoS-in-Teams.md)