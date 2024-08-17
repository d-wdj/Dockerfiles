ARG TAG_HTSLIB=1.20--h5efdd21_2
ARG TAG_SAMTOOLS=1.20--h50ea8bc_1
ARG TAG_BCFTOOLS=1.20--h8b25389_1

FROM quay.io/biocontainers/htslib:$TAG_HTSLIB as htslib
FROM quay.io/biocontainers/samtools:$TAG_SAMTOOLS as samtools
FROM quay.io/biocontainers/bcftools:$TAG_BCFTOOLS as bcftools

COPY --from=htslib /usr/local/bin/tabix /usr/local/bin/tabix
COPY --from=samtools /usr/local/bin/samtools /usr/local/bin/samtools
