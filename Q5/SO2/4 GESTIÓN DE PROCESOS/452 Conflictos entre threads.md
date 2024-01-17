En casos que pueden haber conflictos entre threads (Race Conditions) se fuerza una secuencialización de segmentos de código que lo puedan sufrir a través de marcar "zonas de exclusión mutua" (atomic o critical en OpenMP).

