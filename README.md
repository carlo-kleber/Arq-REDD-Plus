# Arq-REDD+

A technology-agnostic reference architecture for carbon credit management in Blockchain-based REDD+ projects.

Supplementary material for the manuscript *Arq-REDD+: An Agnostic Architectural Model for Carbon Credit Management in Blockchain-Based REDD+ Projects*, by Marcela Ceschim Caburlão and Carlo Kleber da Silva Rodrigues, Universidade Federal do ABC (UFABC).

## Architectural specification

- [Overview](architecture/README.md)
- [Foundations](architecture/foundations.md)
- [Network Layer](architecture/network-layer.md)
- [Consensus Layer](architecture/consensus-layer.md)
- [Application Layer](architecture/application-layer.md)
- [Credit life cycle](architecture/credit-lifecycle.md)
- [External data trust and MRV](architecture/external-data-trust.md)
- [Interoperability](architecture/interoperability.md)
- [Governance and security](architecture/governance-security.md)

## Requirements and interfaces

- [Requirements catalogue](requirements/catalogue.md)
- [Requirements-to-component traceability](requirements/traceability.md)
- [Interface contracts](interfaces/interface-contracts.md)

## Configurations and evaluation

- [Technological decision points](configurations/technological-decisions.md)
- [Compatibility constraints](configurations/compatibility.md)
- [Contrasting configurations](configurations/contrasting-configurations.md)
- [Architectural evaluation scenarios](evaluation/scenarios.md)
- [Complementary simulation evaluation](simulation/README.md)

## Scope and reproducibility

The documentation describes 13 requirements, 15 functional components, 10 interface contracts, 10 technological decision points, two candidate configurations and eight analytical scenarios. It specifies design-time flexibility subject to compatibility constraints, not seamless migration or demonstrated interoperability.

The original simulation code and experimental materials are available at https://github.com/mCaburlao/Arq-REDD-. Consult that repository for its license, attribution and execution instructions. The simulation evaluates selected network and consensus properties of one instantiation. No independent reproduction is claimed here.

## Citation

See [CITATION.cff](CITATION.cff). The accompanying manuscript is under revision; no publication DOI is asserted.

## License

Original architectural documentation is licensed under [CC BY 4.0](LICENSE.md). Third-party materials and upstream simulation software retain their applicable licenses.
