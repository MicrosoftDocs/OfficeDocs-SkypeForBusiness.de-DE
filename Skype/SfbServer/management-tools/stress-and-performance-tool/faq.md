---
title: Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), hilfreich, um herauszufinden, welche Toolkonfigurationen unterstützt werden, um Toolprobleme zu beheben und Verhaltensweisen zu erläutern, die beim Ausführen der Stress- und Leistungstools auftreten können.
ms.openlocfilehash: fb81d31711b027d58b8d5b97ecd6d14f32c0fa0f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857292"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool
 
Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), hilfreich, um herauszufinden, welche Toolkonfigurationen unterstützt werden, um Toolprobleme zu beheben und Verhaltensweisen zu erläutern, die beim Ausführen der Stress- und Leistungstools auftreten können.
  
 Diese häufig gestellten Fragen behandeln einige der am häufigsten gestellten Fragen zum Stress- und Leistungstool Skype for Business Server 2015 und können bei der Problembehandlung und der Toolkonfiguration hilfreich sein.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool.exe in der Produktion ausführen?

Dies wird **nicht** empfohlen. Das Tool würde sich auf die Leistung, Sicherheit und Endbenutzerfreundlichkeit Ihres Produktionsservers auswirken.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Ich protokolliere meine Benutzer zum ersten Mal. Warum führen meine Server eine hohe Last aus?

Wenn sich die Benutzer zum ersten Mal anmelden, werden zusätzliche Vorgänge im Hintergrund ausgeführt. Daher kann die Leistung auf dem Microsoft SQL Server Back-End-Server beeinträchtigt werden. Es wird empfohlen, einen kurzen Test auszuführen, der sich bei allen Benutzern anmeldet, und dann die Clients neu zu starten, bevor Sie mit der Messung der Ergebnisse mit dem Tool beginnen. Skype for Business Server unterstützt nicht mehr als 12 gleichzeitige Benutzeranmeldungssitzungen pro Sekunde, aber bitte beachten Sie, dass die tatsächliche Anzahl, die von Ihren Servern verarbeitet werden kann, von Ihrer Hardwarekonfiguration abhängt und möglicherweise niedriger als der unterstützte Wert ist.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meinen Clients geht der Arbeitsspeicher aus! Wie behebe ich diese Situation?

Wenn clients nicht genügend Arbeitsspeicher vorhanden ist, sollten Sie die Anzahl der Benutzer reduzieren, die pro Skype for Business Server Front-End-Pool angemeldet sind. Sie können auch auswählen, ob Front-End-Pools skaliert werden sollen, wenn das Problem dauerhaft ist.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Kann ich dieses Tool auf einem Skype for Business Server selbst ausführen?

Sie sollten dies nicht tun. Dieses Szenario wird nicht unterstützt, da es aufgrund eines binären Konflikts fehlschlagen kann und weil das Ziel darin besteht, den Ressourcenverbrauch auf dem Server zu messen. Wenn das Tool tatsächlich ausgeführt wird, würde sich dies auf die Serverleistung auswirken und Ihre Daten und Messungen ungültig werden.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool.exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?

Ja, das ist möglich.
  
## <a name="what-does-mpop-mean"></a>Was bedeutet MPOP?

MPOP ist eine gekürzte Möglichkeit, "mehrere Anwesenheitspunkte" zu sagen. MPOP soll Szenarien simulieren, in denen Benutzer von mehreren Computern oder Geräten aus beim Skype for Business 2015-Client angemeldet sind. Beachten Sie, dass in LyncPerfTool.exe jeder Endpunkt das Standardprofil verwendet. Mit anderen Worten, das Profil wird nicht zwischen zwei Anwesenheitspunkten aufgeteilt.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich habe mit LyncPerfTool.exe begonnen, aber es passiert nichts. Was ist los?

Überprüfen Sie den Indikator "Aktive Endpunkte insgesamt" auf den Servern, um festzustellen, ob die Benutzer eine Verbindung herstellen. Wenn die Benutzer keine Verbindung herstellen, überprüfen Sie Ihre Skype for Business Server 2015-Konfiguration. Das Angezeigte Problem tritt in der Regel auf, weil ein Servername, ein Benutzerpräfix oder ein Kennwort falsch ist. Beachten Sie, dass externe Clients Access-Proxy- und TargetServer-Werte angeben sollten. Überprüfen Sie die Portnummer in der Konfigurationsdatei.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Wie kann ich sicherstellen, dass etwas gemessen wird?

Es gibt LyncPerfTool-Leistungsindikatoren, die angeben, ob Benutzer Eine Verbindung herstellen und Aktionen ausführen. Die einfachste Möglichkeit, sicherzustellen, dass Aktionen gemessen werden, besteht jedoch darin, sich bei einem der Konten mit einem Skype for Business 2015-Client anzumelden und diese Aktionen selbst auszuführen. Überprüfen Sie die Ergebnisse, um zu bestätigen, dass Messungen durchgeführt wurden.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Ich habe Lync Server 2010 Capacity Planning Tools und/oder Lync Server 2013 Capacity Planning Tools installiert. Ist das in Ordnung?

 Diese Tools haben Interoperabilitätsprobleme! Sie müssen alle vorherigen Versionen dieser Tools deinstallieren, um gültige Daten aus dem Tool Skype for Business Server 2015 Stress and Performance abzurufen.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Richten die Stress- und Leistungstools die CAA-Anrufinformationsservertopologie ein?

Nein, die Tools tun dies nicht. Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten, um die Benutzerlast zu simulieren.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Wie viele Benutzer werden von den Tools maximal unterstützt?

Beim Testen haben wir bis zu 80.000 Benutzer erstellt und Tests ausgeführt, die insgesamt 30.000 Benutzer umfassen, die diese Tools ausführen. Wir empfehlen maximal 120.000 Benutzer, obwohl die technischen Einschränkungen höhere Werte zulassen. Denken Sie daran, dass diese Werte vom Server und der Hardware in Ihrer Umgebung abhängen.
  

