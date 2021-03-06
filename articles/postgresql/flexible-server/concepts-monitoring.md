---
title: Überwachung und Metriken in Azure Database for PostgreSQL Flexible Server
description: In diesem Artikel werden die Überwachungs- und Metrikfeatures in Azure Database for PostgreSQL Flexible Server beschrieben.
author: lfittl-msft
ms.author: lufittl
ms.service: postgresql
ms.topic: conceptual
ms.date: 09/23/2020
ms.openlocfilehash: 1519e0b5cef6055cf8d8b0aded0d8ad323d548a2
ms.sourcegitcommit: 829d951d5c90442a38012daaf77e86046018e5b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91707845"
---
# <a name="monitor-metrics-on-azure-database-for-postgresql---flexible-server"></a>Überwachen von Metriken in Azure Database for PostgreSQL Flexible Server

> [!IMPORTANT]
> Azure Database for PostgreSQL – Flexible Server befindet sich in der Vorschau.

Die Überwachung der Daten zu Ihren Servern unterstützt Sie bei der Problembehandlung und der Optimierung Ihrer Workloads. Azure Database for PostgreSQL bietet verschiedene Überwachungsoptionen, um Einblicke in das Verhalten Ihres Servers zu gewähren.

## <a name="metrics"></a>Metriken
Azure Database for PostgreSQL bietet verschiedene Metriken, die Einblicke in das Verhalten der Ressourcen gewähren, die dem PostgreSQL-Server zugrunde liegen. Jede Metrik wird mit einer Frequenz von einer Minute ausgegeben und verfügt über einen [Verlauf von bis zu 93 Tagen](../../azure-monitor/platform/data-platform-metrics.md#retention-of-metrics). Sie können Warnungen für die Metriken konfigurieren. Darüber hinaus können weitere Optionen wie das Einrichten automatisierter Aktionen, das Durchführen erweiterter Analysen und das Archivieren des Verlaufs ausgeführt werden. Weitere Informationen finden Sie unter [Überblick über Metriken in Microsoft Azure](../../azure-monitor/platform/data-platform-metrics.md).

### <a name="list-of-metrics"></a>Liste der Metriken
Für PostgreSQL Flexible Server sind folgende Metriken verfügbar:


|Metrik|Metrikanzeigename|Einheit|BESCHREIBUNG|
|---|---|---|---|
| active_connections | Die aktiven Verbindungen. | Anzahl | Die Anzahl der Verbindungen mit dem Server | 
| backup_storage_used | Verwendeter Sicherungsspeicher | Byte | Die Menge des verwendeten Sicherungsspeichers. Diese Metrik stellt den gesamten Speicherplatz dar, der von allen vollständigen Datenbanksicherungen, differenziellen Sicherungen und Protokollsicherungen beansprucht wurde, die auf der Grundlage der für den Server festgelegten Beibehaltungsdauer für Sicherungen aufbewahrt wurden. Die Häufigkeit der Sicherungen wird durch den Dienst verwaltet. Bei georedundantem Speicher wird doppelt so viel Sicherungsspeicher genutzt wie bei lokal redundantem Speicher. |
| connections_failed | Verbindungsfehler | Anzahl | Verbindungsfehler. |
| connections_succeeded | Erfolgreiche Verbindungen | Anzahl | Erfolgreiche Verbindungen. |
| cpu_credits_consumed | Verbrauchte CPU-Guthaben | Anzahl | Menge des vom flexiblen Server genutzten Guthabens. Gilt für burstfähige Dienstebenen. |
| cpu_credits_remaining | Verbleibende CPU-Guthaben | Anzahl | Gesamtmenge des Guthabens, das für den Burst verfügbar ist. Gilt für burstfähige Dienstebenen. |
| cpu_percent | CPU in Prozent | Percent | Die CPU-Auslastung in Prozent. | 
| disk_queue_depth | Warteschlangentiefe für Datenträger | Anzahl | Anzahl offener E/A-Vorgänge für den Datenträger. |
| iops | IOPS | Anzahl | Anzahl der E/A-Vorgänge für den Datenträger pro Sekunde. |
| maximum_used_transactionIDs | Maximale Anzahl von verwendeten Transaktions-IDs | Anzahl | Maximal verwendete Transaktions-IDs. |
| memory_percent | Arbeitsspeicher in Prozent | Percent | Die Arbeitsspeicherauslastung in Prozent. |
| network_bytes_egress | Netzwerk ausgehend | Byte | Menge des ausgehenden Netzwerkdatenverkehrs. |
| network_bytes_ingress | Netzwerk eingehend | Byte | Menge des eingehenden Netzwerkdatenverkehrs. |
| read_iops | Lese-IOPS | Anzahl | Anzahl der E/A-Lesevorgänge für den Datenträger pro Sekunde. |
| read_throughput | Lesedurchsatz | Byte | Vom Datenträger pro Sekunde gelesene Byte. |
| storage_free | Freier Speicher | Byte | Menge des verfügbaren Speichers. |
| storage_percent | Speicher in Prozent | Prozentwert | Menge des verwendeten Speichers in Prozent. Der vom Dienst verwendete Speicher kann die Datenbankdateien, Transaktionsprotokolle und Serverprotokolle umfassen.|
| storage_used | Verwendeter Speicher | Byte | Menge des verwendeten Speichers in Prozent. Der vom Dienst verwendete Speicher kann die Datenbankdateien, Transaktionsprotokolle und Serverprotokolle umfassen. |
| txlogs_storage_used | Verwendeter Transaktionsprotokollspeicher | Byte | Menge des von den Transaktionsprotokollen verwendeten Speichers. | 
| write_throughput | Schreibdurchsatz | Byte | Pro Sekunde auf den Datenträger geschriebene Byte. |
| write_iops | Schreib-IOPS | Anzahl | Anzahl der E/A-Schreibvorgänge für den Datenträger pro Sekunde. |

## <a name="server-logs"></a>Serverprotokolle
Azure Database for PostgreSQL ermöglicht es Ihnen, die Standardprotokolle von Postgres zu konfigurieren und darauf zuzugreifen. Weitere Informationen zu Protokollen finden Sie in der [Dokumentation zu Protokollierungskonzepten](concepts-logging.md).
