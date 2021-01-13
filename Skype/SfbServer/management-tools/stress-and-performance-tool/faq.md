---
title: Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), hilfreich, um herauszufinden, welche Toolkonfigurationen unterstützt werden, problembehebung von Toolproblemen und das Erklären von Verhaltensweisen, die Ihnen beim Ausführen der Stress- und Leistungstools auftreten können.
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814965"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Häufig gestellte Fragen zum Skype for Business Server 2015 Stress and Performance Tool
 
Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), hilfreich, um herauszufinden, welche Toolkonfigurationen unterstützt werden, problembehebung von Toolproblemen und das Erklären von Verhaltensweisen, die Ihnen beim Ausführen der Stress and Performance Tools möglicherweise auftreten.
  
 Diese häufig gestellten Fragen enthalten einige der am häufigsten gestellten Fragen zum Skype for Business Server 2015 Stress and Performance-Tool und können bei der Problembehandlung und der Auswahl der Toolkonfiguration hilfreich sein.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool.exe in der Produktion ausführen?

Dies **wird nicht** empfohlen. Das Tool würde sich auf die Leistung, Sicherheit und Endbenutzerleistung des Produktionsservers auswirken.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Ich möchte meine Benutzer zum ersten Mal anmelden. Warum wird auf meinen Servern eine hohe Last ausgeführt?

Bei der ersten Anmeldung der Benutzer werden zusätzliche Vorgänge im Hintergrund ausgeführt. Dies hat zur Folge, dass die Leistung des Microsoft SQL Server Back-End-Servers beeinträchtigt werden kann. Es wird empfohlen, dass Sie einen kurzen Test ausführen, der sich bei allen Benutzern anmeldet, und dann die Clients neu starten, bevor Sie mit der Messung der Ergebnisse mit dem Tool beginnen. Skype for Business Server unterstützt nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde. Beachten Sie jedoch, dass die tatsächliche Anzahl, die von Ihren Servern verarbeitet werden kann, von Ihrer Hardwarekonfiguration abhängt und möglicherweise niedriger als der unterstützte Wert ist.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meine Clients haben nicht mehr genügend Arbeitsspeicher! Was soll ich machen?

Wenn für Clients nicht genügend Arbeitsspeicher verfügbar ist, sollten Sie die Anzahl der Benutzer verringern, die pro Skype for Business Server-Front-End-Pool angemeldet sind. Sie können front-End-Pools auch skalieren, wenn das Problem weiterhin besteht.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Kann ich dieses Tool auf einem Skype for Business-Server selbst ausführen?

Das sollten Sie nicht tun. Dieses Szenario wird nicht unterstützt, da es aufgrund eines binären Konflikts möglicherweise fehlschlägt und weil das Ziel ist, den Ressourcenverbrauch auf dem Server zu messen. Die Ausführung des Tools würde sich auf die Serverleistung auswirken und Ihre Daten und Messungen ungültig werden lassen.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool.exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?

Ja, das können Sie.
  
## <a name="what-does-mpop-mean"></a>Was bedeutet MPOP?

MPOP ist eine verkürzte Möglichkeit, "mehrere Anwesenheitspunkte" zu sagen. MPOP soll Szenarien simulieren, in denen Benutzer von mehreren Computern oder Geräten am Skype for Business 2015-Client angemeldet sind. Beachten Sie, dass in LyncPerfTool.exe Endpunkten das Standardprofil verwendet wird. Anders ausgedrückt: Das Profil wird nicht zwischen zwei Anwesenheitspunkten aufgeteilt.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich habe mit LyncPerfTool.exe begonnen, aber es passiert nichts. Was ist los?

Überprüfen Sie den Leistungsindikator "Aktive Endpunkte insgesamt" auf den Servern, um zu überprüfen, ob die Benutzer eine Verbindung herstellen. Wenn die Benutzer keine Verbindung herstellen, überprüfen Sie Ihre Skype for Business Server 2015-Konfiguration. Das Angezeigte Problem tritt in der Regel auf, weil ein Servername, ein Benutzerpräfix oder ein Kennwort falsch ist. Beachten Sie, dass externe Clients Zugriffsproxy- und Zielserverwerte angeben sollten. Überprüfen Sie die Portnummer in der Konfigurationsdatei.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Wie kann ich sicherstellen, dass etwas gemessen wird?

Es gibt LyncPerfTool-Leistungsindikatoren, die angeben, ob Benutzer eine Verbindung herstellen und Aktionen ausführen. Am einfachsten können Sie jedoch sicherstellen, dass Aktionen gemessen werden, indem Sie sich bei einem der Konten mit einem Skype for Business 2015-Client anmelden und diese Aktionen selbst ausführen. Überprüfen Sie die Ergebnisse, um zu bestätigen, dass Messungen durchgeführt wurden.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Ich habe Lync Server 2010 Capacity Planning Tools und/oder Lync Server 2013 Capacity Planning Tools installiert. Ist das in Ordnung?

 Diese Tools haben Interoperabilitätsprobleme! Sie müssen alle vorherigen Versionen dieser Tools deinstallieren, um gültige Daten aus dem Skype for Business Server 2015 Stress and Performance Tool zu erhalten.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Richten die Belastungs- und Leistungstools die Topologie des CaA-Anrufinformationsservers ein?

Nein, die Tools tun dies nicht. Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten, um die Benutzerlast zu simulieren.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Wie viele Benutzer werden von den Tools maximal unterstützt?

Beim Testen haben wir bis zu 80.000 Benutzer erstellt und Tests mit insgesamt 30.000 Benutzern ausgeführt, die diese Tools ausführen. Wir empfehlen maximal 120.000 Benutzer, obwohl die technischen Einschränkungen höhere Werte zulassen. Denken Sie daran, dass diese Werte vom Server und der Hardware in Ihrer Umgebung abhängen.
  

