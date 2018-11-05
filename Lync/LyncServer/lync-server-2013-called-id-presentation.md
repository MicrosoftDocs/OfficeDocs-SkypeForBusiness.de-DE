---
title: Darstellung der ID des Angerufenen in Lync Server 2013
TOCTitle: Darstellung der ID des Angerufenen in Lync Server 2013
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49890949
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Darstellung der ID des Angerufenen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Mit Lync Server 2010 kann die Telefonnummer des angerufenen Teilnehmers (d. h., die gewählte Telefonnummer) vom E.164-Format in das für den *Trunkpeer* (also das zugeordnete Gateway, Nebenstellensystem oder der zugeordnete SIP-Trunk) erforderliche lokale Wählformat übersetzt werden. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.


> [!IMPORTANT]
> Die Möglichkeit, einer Enterprise-VoIP-Trunkkonfiguration eine oder mehrere Übersetzungsregeln zuzuordnen, bietet eine <EM>Alternative</EM> zur Konfiguration von Übersetzungsregeln für den Trunkpeer. Ordnen Sie einer Enterprise-VoIP-Trunkkonfiguration keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten könnten.



Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel erstellen oder ändern:

  - Geben Sie im Tool **Übersetzungsregel erstellen**Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern an, und lassen Sie anschließend die Lync Server-Systemsteuerung das entsprechende Vergleichsmuster und eine Übersetzungsregel generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.


> [!NOTE]
> Ausführliche Informationen zur Verwendung von regulären Ausdrücken finden Sie in "Reguläre Ausdrücke von .NET Framework" unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0x407</A>.



## In diesem Abschnitt

  - [Erstellen oder Ändern einer Übersetzungsregel mit dem Tool zum Erstellen einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Manuelles Erstellen oder Ändern einer Übersetzungsregel](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## Siehe auch

#### Konzepte

[Darstellung der Anrufer-ID in Lync Server 2013](lync-server-2013-caller-id-presentation.md)

