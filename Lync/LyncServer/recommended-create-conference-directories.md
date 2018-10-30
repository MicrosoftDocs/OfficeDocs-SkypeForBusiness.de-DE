---
title: Erstellen von Konferenzverzeichnissen (empfohlen)
TOCTitle: Erstellen von Konferenzverzeichnissen (empfohlen)
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232638
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von Konferenzverzeichnissen (empfohlen)

 

_**Letztes Änderungsdatum des Themas:** 2014-10-03_

In Konferenzverzeichnissen wird eine Zuordnung der alphanumerischen Besprechungs-ID, die ein Teilnehmer bei Verwendung von Lync 2013 zum Beitreten zu einer Konferenz nutzt, und der rein numerischen Konferenz-ID verwaltet, die ein Einwahlkonferenzteilnehmer zum Beitreten zur Konferenz verwendet. Das Format der Konferenz-ID lautet folgendermaßen:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.

## Erstellen eines Konferenzverzeichnisses

1.  Geben Sie folgendes Cmdlet in Lync Server-Verwaltungsshell ein:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    So wird zum Beispiel ein neues Konferenzverzeichnis mit dem Identitätswert 42 erstellt, das im Pool „atl-cs-001.litwareinc.com“ gehostet wird:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## Siehe auch

#### Konzepte

[Anforderungen für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Weitere Ressourcen

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

