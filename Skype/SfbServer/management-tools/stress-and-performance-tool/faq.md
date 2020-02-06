---
title: Häufig gestellte Fragen zum Skype for Business Server 2015 Stress-und Leistungs Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Häufig gestellte Fragen (FAQ) zu Skype for Business 2015 Stress-und Leistungstools, die nützlich sind, um herauszufinden, welche Tool Konfigurationen unterstützt werden, Problembehandlung bei Tool Problemen und verdeutlichen von Verhaltensweisen, die beim Ausführen der Stress-und Leistungstools angezeigt werden können .
ms.openlocfilehash: 2847ecd54389f64d6961cc72ecb94d87e847b0b0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816184"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Häufig gestellte Fragen zum Skype for Business Server 2015 Stress-und Leistungs Tool
 
Häufig gestellte Fragen (FAQ) zu Skype for Business 2015 Stress-und Leistungstools, die nützlich sind, um herauszufinden, welche Tool Konfigurationen unterstützt werden, Problembehandlung bei Tool Problemen und verdeutlichen von Verhaltensweisen, die beim Ausführen der Stress-und Leistungstools angezeigt werden können .
  
 Diese FAQ umfasst einige der am häufigsten gestellten Fragen zum Skype for Business Server 2015 Stress-und Leistungstool und kann bei der Problembehandlung und bei der Konfiguration von Tools behilflich sein.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool. exe in Production ausführen?

Dies wird **nicht** empfohlen. Das Tool hat Auswirkungen auf die Leistung des Produktionsservers, die Sicherheit und die Benutzeroberfläche.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Ich habe meine Benutzer zum ersten Mal angemeldet. Warum werden meine Server mit einer großen Auslastung belastet?

Wenn sich die Benutzer zum ersten Mal anmelden, werden weitere Vorgänge im Hintergrund ausgeführt. Infolgedessen kann die Leistung auf dem Microsoft SQL Server-Back-End-Server beeinträchtigt werden. Es wird empfohlen, dass Sie einen kurzen Test ausführen, der alle Benutzer anmeldet, und dann die Clients neu starten, bevor Sie mit dem Messen der Ergebnisse mit dem Tool beginnen. Skype for Business Server unterstützt nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde, doch beachten Sie bitte, dass die tatsächliche Zahl, die von ihren Servern verarbeitet werden kann, von Ihrer Hardwarekonfiguration abhängig ist und möglicherweise niedriger als der unterstützte Wert ist.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meine Kunden haben keinen Arbeitsspeicher mehr! Was soll ich tun?

Wenn für Clients der Arbeitsspeicher knapp wird, sollten Sie die Anzahl der Benutzer reduzieren, die pro Skype for Business Server-Front-End-Pool angemeldet sind. Sie können auch festlegen, dass Front-End-Pools skaliert werden, wenn das Problem weiterhin besteht.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Kann ich dieses Tool auf einem Skype for Business-Server selbst ausführen?

Das sollten Sie nicht tun. Dieses Szenario wird nicht unterstützt, da es möglicherweise aufgrund eines binären Konflikts fehlschlägt, und auch, weil das Ziel darin besteht, den Ressourcenverbrauch auf dem Server zu messen. Wenn Sie das Tool tatsächlich ausführen, würde dies die Serverleistung beeinträchtigen und Ihre Daten und Maße ungültig machen.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool. exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?

Ja, das ist möglich.
  
## <a name="what-does-mpop-mean"></a>Was bedeutet mpop?

MPOP ist eine verkürzte Möglichkeit, "mehrere Anwesenheits Punkte" zu sagen. MPOP soll Szenarien simulieren, in denen Benutzer auf mehreren Computern oder Geräten bei Skype for Business 2015-Client angemeldet sind. Beachten Sie, dass in LyncPerfTool. exe jeder Endpunkt das Standardprofil verwendet. Anders ausgedrückt: das Profil wird nicht zwischen zwei Anwesenheits Punkten aufgeteilt.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich habe LyncPerfTool. exe gestartet, aber es geschieht nichts. Was ist los?

Überprüfen Sie den Indikator Gesamtzahl aktiver Endpunkte auf den Servern, um festzustellen, ob die Benutzer eine Verbindung herstellen. Wenn die Benutzer keine Verbindung herstellen, überprüfen Sie Ihre Skype for Business Server 2015-Konfiguration. Das angezeigte Problem tritt in der Regel auf, weil einer der Servernamen, das Benutzerpräfix oder das Kennwort falsch ist. Beachten Sie, dass externe Clients Zugriffs Proxy-und TargetServer-Werte angeben sollten. Überprüfen Sie die Portnummer in der Konfigurationsdatei.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Wie kann ich sicher sein, dass etwas gemessen wird?

Es gibt LyncPerfTool-Leistungsindikatoren, die angeben, ob Benutzer eine Verbindung herstellen und Aktionen ausführen, doch am einfachsten können Sie sicherstellen, dass die Aktionen gemessen werden, indem Sie sich bei einem der Konten mit einem Skype for Business 2015-Client anmelden und diese ausführen. Aktionen selbst durchführen. Überprüfen Sie die Ergebnisse, um zu bestätigen, dass Messungen durchgeführt wurden.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Ich habe lync Server 2010-Kapazitätsplanungstools und/oder lync Server 2013-Kapazitätsplanungstools installiert. Ist das in Ordnung?

 Diese Tools haben Interoperabilitätsprobleme! Sie müssen alle vorherigen Versionen dieser Tools deinstallieren, um gültige Daten aus dem Stress-und Leistungstool von Skype for Business Server 2015 zu erhalten.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Werden die Stress-und Leistungstools die CAA-Anruf Informationsserver-Topologie einrichten?

Nein, die Tools werden dies nicht tun. Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten, um die Benutzerauslastung zu simulieren.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Was ist die maximale Anzahl von Benutzern, die von den Tools unterstützt werden?

In Testphase haben wir bis zu insgesamt 80.000-Benutzer erstellt und Tests mit insgesamt 30.000 Benutzern ausgeführt, die diese Tools ausführen. Wir empfehlen maximal 120.000-Benutzer, auch wenn die technischen Einschränkungen höhere Werte zulassen. Beachten Sie, dass diese Werte vom Server und der Hardware in Ihrer Umgebung abhängen.
  

