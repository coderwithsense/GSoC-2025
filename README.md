# GSoC 2025 Final Report: Forecast.bid - A Gamified Token Price Prediction Protocol

**Name:** Himanshu Poptani

**Organization:** [Australian Open Source Software Innovation and Education (AOSSIE)](https://www.aossie.org/)

**GitHub:** [https://github.com/coderwithsense](https://github.com/coderwithsense)

**Social Profiles:** [LinkedIn](https://www.linkedin.com/in/himanshu-poptani)

**Project:** Forecast.bid: A Decentralized, Gamified Token Price Prediction Protocol on EVM-Compatible Blockchains

## 1. Project Overview

Forecast.bid is a fully decentralized prediction market platform built on EVM-compatible blockchains that enables users to speculate on cryptocurrency token prices in a transparent and trustless manner. The platform allows anyone to create binary prediction markets where participants bet on whether a token's price will be above or below a target price at a specified expiry time.

The core problem this project solves is the lack of accessible, decentralized prediction markets that combine simplicity with gamification. Traditional prediction markets are often centralized, opaque, or require complex interactions. Forecast.bid eliminates intermediaries by implementing all logic on-chain through smart contracts, integrating Chainlink price feeds for reliable price data, and providing an intuitive user interface for seamless Web3 interaction.

The initial scope proposed for GSoC included developing modular smart contracts (PredictionFactory, PredictionPool, and Oracle integration), building a responsive Next.js frontend with wallet integration, and eliminating the need for traditional backend infrastructure by leveraging on-chain data exclusively. The project successfully delivered a serverless, 100% decentralized architecture where users can create markets, mint BULL/BEAR tokens, exit positions early with dynamic fees, and claim rewards based on actual price outcomes verified through Chainlink oracles.

## 2. Accomplishments and Completed Goals

Throughout the GSoC period, the project exceeded initial expectations by delivering a production-ready decentralized prediction market with comprehensive smart contract architecture, seamless frontend integration, and complete elimination of centralized backend dependencies. The work was divided into multiple development phases focusing on contract development, testing, deployment, and frontend implementation.

### Key Accomplishments:

* **Modular Smart Contract Architecture:** Successfully designed and implemented a factory pattern with `PredictionFactory.sol` handling pool creation and registry, and `PredictionPool.sol` managing individual prediction markets. The contracts feature dynamic fee mechanisms, pagination support for scalability, and comprehensive documentation with 400+ lines of inline comments explaining architecture decisions and gas optimization strategies.

* **Chainlink Oracle Integration:** Integrated Chainlink Price Feeds for trustless price data retrieval, enabling decentralized settlement without relying on centralized APIs. The oracle integration supports multiple token pairs and provides accurate, tamper-proof price snapshots for market resolution.

* **Complete Serverless Architecture:** Achieved the ambitious goal of eliminating all backend API endpoints and database dependencies. Initially, the proposal included MongoDB/Prisma for metadata storage, but through architectural refinement, all game logic, state management, and data retrieval were moved entirely on-chain, making the platform truly decentralized and censorship-resistant.

* **Multi-Chain Deployment:** Successfully deployed and verified contracts on Polygon Amoy testnet and Sepolia testnet using Hardhat, with verification on PolygonScan and EtherscanSepolia. This demonstrates cross-chain compatibility and prepares the platform for future mainnet deployment.

* **Comprehensive Testing Suite:** Developed extensive unit and integration tests using Hardhat's testing framework, covering all contract functions including edge cases for minting, burning, fee calculations, snapshot logic, and reward distribution. The test suite ensures contract reliability and security before deployment.

* **Dynamic Fee System:** Implemented a progressive fee mechanism where fees start at 0% and linearly increase to 100% in the final 24 hours before expiry. This innovative approach encourages early participation while preventing last-minute manipulation, with fees split 50/50 between protocol and creator.

* **Modern Frontend with Web3 Integration:** Built a responsive, aesthetically pleasing UI using Next.js 14, Tailwind CSS, and Shadcn components. Integrated Wagmi and RainbowKit for seamless wallet connectivity supporting MetaMask, WalletConnect, and other popular wallets. The frontend features real-time contract interaction, countdown timers, pool creation forms with validation, and detailed pool pages showing live statistics.

* **Developer Experience Improvements:** Organized codebase with clear separation between contract ABIs, addresses, and configuration files. Added comprehensive README documentation for both repositories with setup instructions, deployment guides, and architecture explanations to facilitate future contributions.

## 3. Summary of Work and Link to Pull Requests

### Smart Contract Repository ([Destiny-Solidity](https://github.com/StabilityNexus/Destiny-Solidity))

| Commit Hash | Description | Status |
| :---- | :---- | :---- |
| [cefae5e](https://github.com/StabilityNexus/Destiny-Solidity/commit/cefae5e) | New deployments of contracts on Polygon Amoy and Sepolia with updated ABIs | ✅ Completed |
| [9da2b85](https://github.com/StabilityNexus/Destiny-Solidity/commit/9da2b85) | Implemented changes from mentor code review feedback | ✅ Completed |
| [a27a8e5](https://github.com/StabilityNexus/Destiny-Solidity/commit/a27a8e5) | Updated contracts using Hardhat, deployed on Polygon and Sepolia, verified on block explorers using hardhat-verify | ✅ Completed |
| [f44b969](https://github.com/StabilityNexus/Destiny-Solidity/commit/f44b969) | Fixed issues mentioned in code review comments | ✅ Completed |
| [fc60ff1](https://github.com/StabilityNexus/Destiny-Solidity/commit/fc60ff1) | Fixed minor issues in PredictionPool.sol contract logic | ✅ Completed |
| [08f012a](https://github.com/StabilityNexus/Destiny-Solidity/commit/08f012a) | Major changes in PredictionPool contract structure with 278 insertions | ✅ Completed |
| [592bfaf](https://github.com/StabilityNexus/Destiny-Solidity/commit/592bfaf) | Removed obsolete test file (717 deletions) | ✅ Completed |
| [fedc038](https://github.com/StabilityNexus/Destiny-Solidity/commit/fedc038) | Successfully deployed contracts on Sepolia and Polygon Amoy testnets | ✅ Completed |
| [b03a397](https://github.com/StabilityNexus/Destiny-Solidity/commit/b03a397) | Updated contracts, created comprehensive test suite, updated README with setup instructions, configured Hardhat for localhost and Etherscan plugin, updated deployment scripts | ✅ Completed |
| [e7dd73c](https://github.com/StabilityNexus/Destiny-Solidity/commit/e7dd73c) | Refactored code structure for improved readability and maintainability | ✅ Completed |
| [8a9fed7](https://github.com/StabilityNexus/Destiny-Solidity/commit/8a9fed7) | Added PredictionFactory module and integration tests with PredictionPool (50k+ insertions) | ✅ Completed |
| [ebfd465](https://github.com/StabilityNexus/Destiny-Solidity/commit/ebfd465) | Implemented PredictionPool contract with minting, burning, and claiming functionalities | ✅ Completed |
| [8510e24](https://github.com/StabilityNexus/Destiny-Solidity/commit/8510e24) | Added PredictionFactory and PredictionPool contracts with basic functionality framework | ✅ Completed |
| [861688a](https://github.com/StabilityNexus/Destiny-Solidity/commit/861688a) | Downgraded to Hardhat v2 for Chainlink plugin compatibility (migration to v3 planned for future) | ✅ Completed |
| [5b46479](https://github.com/StabilityNexus/Destiny-Solidity/commit/5b46479) | Initialized Hardhat project structure with TypeScript configuration | ✅ Completed |

### Frontend Repository ([Destiny-EVM](https://github.com/StabilityNexus/Destiny-EVM))

| Commit Hash | Description | Status |
| :---- | :---- | :---- |
| [4501fc9](https://github.com/StabilityNexus/Destiny-EVM/commit/4501fc9) | Updated UI to reflect new contract addresses after redeployment | ✅ Completed |
| [36a8d16](https://github.com/StabilityNexus/Destiny-EVM/commit/36a8d16) | Updated contract addresses for Sepolia and Amoy testnets without frontend changes | ✅ Completed |
| [7eeaf60](https://github.com/StabilityNexus/Destiny-EVM/commit/7eeaf60) | Major contracts structure update (1399 insertions, 780 deletions) | ✅ Completed |
| [889c54e](https://github.com/StabilityNexus/Destiny-EVM/commit/889c54e) | Implemented essential changes from code review feedback | ✅ Completed |
| [1c63e89](https://github.com/StabilityNexus/Destiny-EVM/commit/1c63e89) | Unified UI design for contract pool creation page | ✅ Completed |
| [245c4c3](https://github.com/StabilityNexus/Destiny-EVM/commit/245c4c3) | Fixed build errors in production deployment | ✅ Completed |
| [4e594a0](https://github.com/StabilityNexus/Destiny-EVM/commit/4e594a0) | Implemented better rounded UI elements for improved aesthetics | ✅ Completed |
| [5601e52](https://github.com/StabilityNexus/Destiny-EVM/commit/5601e52) | Removed all API endpoints and related code for fetching games, added pool details page with Polygon and Sepolia interaction (928 insertions) | ✅ Completed |
| [6152e20](https://github.com/StabilityNexus/Destiny-EVM/commit/6152e20) | Added trial contracts section, integrated Chainlink price feeds from documentation, created PriceFeedSelector component, modified factory page for pair selection | ✅ Completed |
| [d1c7a3a](https://github.com/StabilityNexus/Destiny-EVM/commit/d1c7a3a) | Implemented CreatePoolPage and PoolDetailPage components with form validation and data visualization (905 insertions) | ✅ Completed |
| [daaa7d0](https://github.com/StabilityNexus/Destiny-EVM/commit/daaa7d0) | Updated PredictionFactory and PredictionPool ABIs with new events and parameters (922 insertions) | ✅ Completed |
| [cf7ca19](https://github.com/StabilityNexus/Destiny-EVM/commit/cf7ca19) | Updated wallet configuration to include Polygon Amoy and adjusted chain settings | ✅ Completed |
| [6843234](https://github.com/StabilityNexus/Destiny-EVM/commit/6843234) | Deleted entire src/app/api directory (406 deletions) - transitioned to fully serverless architecture | ✅ Completed |
| [231c298](https://github.com/StabilityNexus/Destiny-EVM/commit/231c298) | Refactored game components, enhanced GameFeed with search and filters (713 insertions) | ✅ Completed |
| [91c5f0c](https://github.com/StabilityNexus/Destiny-EVM/commit/91c5f0c) | Code sanity improvements, removed unused imports, fixed types and interfaces, added missing interfaces for Game, Position, Transaction, and GameState | ✅ Completed |
| [4957165](https://github.com/StabilityNexus/Destiny-EVM/commit/4957165) | Added prediction pools functionality with new components and UI updates, including countdown timers and improved layout (501 insertions) | ✅ Completed |
| [2f07e0f](https://github.com/StabilityNexus/Destiny-EVM/commit/2f07e0f) | Added prediction pool functionality with hooks and UI for managing price feeds and pools, created /try-contracts endpoints for testing contract functions | ✅ Completed |
| [887b1de](https://github.com/StabilityNexus/Destiny-EVM/commit/887b1de) | Implemented price feed management and pool functionality with custom hooks | ✅ Completed |
| [f69c2aa](https://github.com/StabilityNexus/Destiny-EVM/commit/f69c2aa) | Refactored by removing unused API routes and store files (559 deletions) | ✅ Completed |
| [615f844](https://github.com/StabilityNexus/Destiny-EVM/commit/615f844) | Major refactor of wallet integration to use Wagmi and RainbowKit (4618 insertions) | ✅ Completed |
| [21f9905](https://github.com/StabilityNexus/Destiny-EVM/commit/21f9905) | Centralized chain config and RPC URLs in config.ts for maintainability | ✅ Completed |
| [e9d7de3](https://github.com/StabilityNexus/Destiny-EVM/commit/e9d7de3) | Organized contract ABIs, addresses, and feeds under lib directory (726 insertions) | ✅ Completed |
| [00d8441](https://github.com/StabilityNexus/Destiny-EVM/commit/00d8441) | Added try-contracts page for interacting with trial contracts and testing functionality (309 insertions) | ✅ Completed |
| [fd277fc](https://github.com/StabilityNexus/Destiny-EVM/commit/fd277fc) | Improved app structure, added Zustand stores and types for modularity | ✅ Completed |

## 4. Challenges Faced

### Challenge 1: Transitioning from Backend-Dependent to Fully Serverless Architecture

**Problem:** The initial proposal included a Next.js API backend with MongoDB and Prisma for storing game metadata, user data, and handling snapshots. As development progressed, it became clear that relying on a centralized database contradicted the core Web3 principle of decentralization and introduced a single point of failure.

**Solution:** After consulting with mentors and reviewing the project architecture, the decision was made to eliminate the backend entirely. All API endpoints (game creation, fetching, snapshot triggering) were removed, and functionality was moved on-chain. This required restructuring smart contracts to support efficient data retrieval through view functions, implementing pagination in the factory contract to prevent gas issues when fetching large pool lists, and optimizing the frontend to query blockchain data directly using Wagmi hooks. The result was a truly serverless, censorship-resistant platform.

**Learning:** This challenge taught me the importance of architectural decisions in decentralized systems. I learned that what seems convenient in traditional web development (databases, API caching) can undermine the trustless nature of blockchain applications. It also pushed me to optimize smart contracts for gas efficiency while maintaining rich queryability.

### Challenge 2: Implementing Dynamic Fee Calculations and Time-Based Logic

**Problem:** The project required a sophisticated fee mechanism where fees start at 0% and linearly increase to 100% in the final 24 hours before pool expiry. This needed to work perfectly across different timezones, handle edge cases (pools created less than 24 hours before expiry), and prevent manipulation while remaining gas-efficient.

**Solution:** Implemented a mathematical formula in the `fee()` view function that calculates elapsed time from a reference point (24 hours before expiry) and computes a proportional fee. Extensive testing was conducted with various pool durations and timestamps to ensure accuracy. The implementation uses integer arithmetic to avoid floating-point issues and handles all edge cases including expired pools (100% fee to prevent trading) and new pools (0% fee initially).

**Learning:** This challenge deepened my understanding of time-based smart contract logic, Solidity's timestamp handling, and the importance of thorough edge case testing. It also highlighted how critical mathematical precision is in financial smart contracts where even small rounding errors can be exploited.

### Challenge 3: Multi-Chain Deployment and Contract Verification

**Problem:** Deploying identical contracts across multiple testnets (Polygon Amoy and Sepolia) while maintaining different Chainlink price feed addresses, managing separate contract addresses for the frontend, and verifying contracts on different block explorers proved complex.

**Solution:** Created a robust Hardhat configuration with network-specific settings, implemented environment variable management for sensitive data (private keys, API keys), and developed deployment scripts that automatically handle network detection and configuration. Used Hardhat's verification plugin with proper constructor arguments to verify contracts on PolygonScan and Etherscan. Organized contract addresses and ABIs in the frontend repository in a structured manner (lib/contracts/) to easily switch between networks.

**Learning:** Gained practical experience in production-level deployment workflows, learned the importance of automation in multi-chain development, and understood how to structure projects for scalability across different EVM chains. This experience will be invaluable for future mainnet deployments.

## 5. Learnings and Takeaways

This GSoC project was an intensive learning experience that significantly expanded my technical skills and understanding of decentralized systems. Key learnings include:

* **Advanced Solidity Development:** Mastered complex smart contract patterns including factory pattern implementation, dynamic fee calculations, pagination for gas optimization, and comprehensive event emission for frontend integration. Learned to write production-ready contracts with extensive inline documentation and security considerations.

* **Blockchain Oracles and Chainlink Integration:** Gained hands-on experience integrating Chainlink Price Feeds for decentralized price data, understanding oracle mechanics, handling price feed decimals normalization, and designing contracts that depend on external data sources while maintaining trustlessness.

* **Hardhat Ecosystem Mastery:** Became proficient with Hardhat v2, including writing comprehensive test suites with Mocha/Chai, deploying to multiple testnets, using hardhat-verify for contract verification, and configuring complex network settings. Learned the tradeoffs between Hardhat v2 and v3, particularly regarding plugin compatibility.

* **Modern Web3 Frontend Development:** Advanced skills in Next.js 14 with App Router, mastered Wagmi v2 for React hooks-based blockchain interaction, implemented RainbowKit for beautiful wallet connection UI, and learned to build responsive designs with Tailwind CSS and Shadcn components. Understood the complexities of managing blockchain state in React applications.

* **Serverless Architecture Design:** Learned to design fully decentralized applications without traditional backend infrastructure, understanding tradeoffs between on-chain storage costs and centralized database convenience, and implementing efficient data retrieval patterns using smart contract view functions and pagination.

* **Gas Optimization Techniques:** Developed practical skills in reducing transaction costs through efficient storage patterns, using `unchecked` blocks for safe arithmetic, minimizing storage operations, and choosing appropriate data structures (arrays vs mappings) based on access patterns.

* **Open Source Collaboration:** Gained experience working with mentors through regular code reviews, learned to write clear commit messages, structure pull requests effectively, maintain comprehensive documentation, and communicate technical decisions. Understood the importance of making code accessible for future contributors.


## Screenshots

[Section reserved for project screenshots]

<img width="1470" height="700" alt="Screenshot 2025-10-27 at 2 07 21 PM" src="https://github.com/user-attachments/assets/2d38f2b9-11c9-40ab-b81f-d37c655972e4" />
<img width="1469" height="776" alt="Screenshot 2025-10-27 at 2 07 34 PM" src="https://github.com/user-attachments/assets/84b4dca5-7396-4054-a35b-aad0149d1815" />
<img width="1470" height="769" alt="Screenshot 2025-10-27 at 2 08 21 PM" src="https://github.com/user-attachments/assets/2c0937e5-da93-441b-b019-78e07688f102" />
<img width="1470" height="774" alt="Screenshot 2025-10-27 at 2 08 43 PM" src="https://github.com/user-attachments/assets/867f867c-3aee-48ba-b27d-9dd7dbc4db8a" />
<img width="1470" height="616" alt="Screenshot 2025-10-27 at 2 09 01 PM" src="https://github.com/user-attachments/assets/470848c8-24b6-429d-8c04-4af91a52b389" />



