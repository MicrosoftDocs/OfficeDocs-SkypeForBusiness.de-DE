---
title: Überwachen des Mobilitätsdiensts und der Verwendung der UCWA
TOCTitle: Überwachen des Mobilitätsdiensts und der Verwendung der UCWA
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690025(v=OCS.15)
ms:contentKeyID: 49294601
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überwachen des Mobilitätsdiensts und der Verwendung der UCWA

 

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Sie sollten regelmäßig die CPU- und Speicherauslastung durch den Lync Server-Mobilitätsdienst (Mcx) und die Unified Communications-Web-API (UCWA) anhand der folgenden Angaben überwachen. Zum Überwachen der Auslastung können Sie Folgendes verwenden:

**Für die Unified Communications-Web-API (UCWA)**

  - Der Arbeitsprozess **LyncUcwa** in Internetinformationsdienste-Manager (IIS). Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.

  - Die Leistungsindikatoren **CPU** und **Prozessor**.

Bei den meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte die in [Überwachen der Serverspeicher-Kapazitätslimits](lync-server-2013-monitoring-for-server-memory-capacity-limits.md) beschriebenen Grenzwerte nicht überschreiten.

Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:

  - **LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503 - Dienst nicht verfügbar" fehl.

  - **ASP.NET\\Requests Queued** (sollte immer Null sein).


> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer, die die Webdienste hosten, überarbeiten und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.



**Für den Mobilitätsdienst (Mcx):**

  - Die Arbeitsprozesse **CSIntMcxAppPool** und **CSExtMcxAppPool** in Internetinformationsdienste-Manager (IIS). Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.

  - Die Leistungsindikatoren **CPU** und **Prozessor**.

Bei den meisten Bereitstellungen sollte die Mobilitätsdienst-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Speicherauslastung sollte die in [Überwachen der Serverspeicher-Kapazitätslimits](lync-server-2013-monitoring-for-server-memory-capacity-limits.md) beschriebenen Grenzwerte nicht überschreiten.

Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:

  - **ASP.NET v2.0.50727\\Requests Current**, der die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503 - Dienst nicht verfügbar" fehl.

  - **ASP.NET\\Requests Queued** (sollte immer Null sein).


> [!NOTE]
> Wenn diese Werte erreicht oder überschritten werden, sollten Sie die Kapazitätsplanung für die Computer, die die Webdienste hosten, überarbeiten und die Größenanpassung für die CPU, die Anzahl von Kernen sowie den Arbeitsspeicher neu berechnen.



## Siehe auch

#### Konzepte

[Überwachen der Serverspeicher-Kapazitätslimits](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

