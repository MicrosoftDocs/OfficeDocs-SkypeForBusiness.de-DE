---
title: Häufig gestellte Fragen zu den Skype für Business Server 2015 Stress and Performance-Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 'Skype für Business 2015 Stress and Performance-Tool: häufig gestellte Fragen (FAQ), nützlich für Sie herausfinden, welche Toolkonfigurationen unterstützt werden und Problembehandlung bei Tool zur Klärung Verhalten hin, die bei der Ausführung der Stress and Performance-Tools angezeigt werden .'
ms.openlocfilehash: 604644d5aecb12f94304d1c7ce271c68208e1964
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906746"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Häufig gestellte Fragen zu den Skype für Business Server 2015 Stress and Performance-Tool
 
Skype für Business 2015 Stress and Performance-Tool: häufig gestellte Fragen (FAQ), nützlich für Sie herausfinden, welche Toolkonfigurationen unterstützt werden und Problembehandlung bei Tool zur Klärung Verhalten hin, die bei der Ausführung der Stress and Performance-Tools angezeigt werden .
  
 Diese Fragen und Antworten befasst sich einige der am häufigsten gestellten Fragen zu den Skype für Business Server 2015 Stress and Performance-Tool und können Ihnen bei der Problembehandlung und Tool Konfigurationsoptionen.
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool.exe in der Produktion werden ausgeführt?

Dies wird **nicht** empfohlen. Das Tool würde die Produktion-Server-Leistung, Sicherheit und durch die Endbenutzer beeinträchtigen.
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>Ich bin meine Benutzer zum ersten Mal anmelden. Warum werden meine Server eine hohe Auslastung ausgeführt?

Die Benutzer, melden Sie sich zum ersten Mal zusätzliche Vorgänge im Hintergrund ausgeführt. Daher kann die Leistung auf Microsoft SQL Server Back-End-Server beeinträchtigt werden. Es wird empfohlen, dass Sie einen kurzen Test, der Protokolle auf alle Benutzer ausführen, und die Clients neu starten, bevor Sie, zur Bewertung der Ergebnisse mit dem Tool beginnen. Skype für Business Server nicht mehr als 12 gleichzeitige Benutzer anmeldesitzungen pro Sekunde unterstützen, aber Bedenken hängt von der Hardwarekonfiguration die tatsächliche Anzahl an, die von den Servern verarbeitet werden kann und möglicherweise niedriger als der unterstützte Wert.
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meine Clients sind nicht genügend Arbeitsspeicher ausführen! Was soll ich tun?

Wenn Clients nicht genügend Arbeitsspeicher ausführen, sollten Sie die Anzahl der Benutzer pro Skype für Business Server-Front-End-Pool angemeldet reduzieren. Sie können auch out Front-End-Pools skalieren, wenn das Problem beständig sind.
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Kann ich dieses Tool auf einen Skype für Business Server selbst werden ausgeführt?

Sie sollten nicht dafür. In diesem Szenario wird nicht unterstützt, da sie möglicherweise aufgrund übereinstimmender binary nicht und auch, da das Ziel besteht darin, Ressourcenverbrauch auf dem Server zu messen. Tatsächlich es Ausführung des Tools würde auswirken und Ihre Daten und Maßangaben ungültig.
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool.exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 werden ausgeführt?

Ja, können Sie.
  
## <a name="what-does-mpop-mean"></a>Was bedeutet MPOP?

MPOP ist eine verkürzte Möglichkeit der Aufschrift "multiple Points of Presence". MPOP soll Szenarien, in dem Benutzer Skype für Business 2015 Client aus mehreren Computern oder Geräten angemeldet sind. Bedenken Sie, dass in LyncPerfTool.exe, jeden Endpunkt Standardprofil verwendet wird. Das Profil ist nicht mit anderen Worten, zwischen zwei Points of Presence, aufgeteilt.
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich LyncPerfTool.exe gestartet, aber nichts geschehen ist. Was ist los?

Überprüfen Sie den Leistungsindikator Gesamtanzahl der aktiven Endpunkte auf den Servern, um festzustellen, ob der Benutzer eine Verbindung herstellen. Wenn der Benutzer eine Verbindung herstellen, werden nicht, überprüfen Sie Ihre Skype für Business Server 2015 Konfiguration. Das Problem aus, das Sie in der Regel kennen tritt auf, weil Servernamen, Benutzerpräfix oder Kennwort falsch ist. Beachten Sie, dass externe Clients Zugriffsproxy und Zielserver Werte angeben müssen. Überprüfen Sie die Portnummer in der Konfigurationsdatei.
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>Wie kann ich sicher sein, dass etwas gemessen wird?

Es gibt LyncPerfTool-Leistungsindikatoren, die angeben, ob Benutzer eine Verbindung herstellen und Aktionen ausführen, aber die einfachste Möglichkeit, um sicherzustellen, dass Aktionen gemessen ist, melden Sie sich an einem Konto mit einem Skype für Business 2015 Client, und führen die Aktionen selbst. Überprüfen Sie, dass die Ergebnisse zu bestätigen Maßangaben erstellt wurden.
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 Capacity Planning Tools und/oder Lync Server 2013 Capacity Planning Tools installiert habe. Ist das so richtig?

 Diese Tools haben Interoperabilitätsprobleme im Zusammenhang mit! Sie müssen alle vorherigen Versionen von diese Tools zum Abrufen von gültiger Daten aus der Skype für Business Server 2015 Stress and Performance-Tool deinstallieren.
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Werden Stress and Performance-Tools werden die Servertopologie CAA Call Information eingerichtet?

Nein, nicht die Tools dies. Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten, um Benutzerlast zu simulieren.
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Was ist die maximale Anzahl der Benutzer, die Tools unterstützt?

Testen, haben wir bis zu 80.000 Benutzern insgesamt erstellt, und Tests Ausführen dieser Tools 30.000 Benutzer insgesamt ausgeführt. Wir empfehlen maximal 120.000 Benutzer, obwohl die technischen Einschränkungen für eine höhere Werte zulassen. Denken Sie daran, dass diese Werte auf dem Server und der Hardware in Ihrer Umgebung abhängen.
  

