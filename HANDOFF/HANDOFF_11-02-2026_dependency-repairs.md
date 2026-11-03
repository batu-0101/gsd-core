# Dependency security repair

Consolidated the open dependency update work with current security fixes. Updated Fallow, qs, affected transitive packages and ESLint. Patched glob/minimatch through overrides; migrated the two local ESLint rules to the supported filename property. New recommended lint checks required removing overwritten initial values and retaining original exception causes. Test assertions and lint rules were not weakened.

Verification: npm audit including development and optional dependencies reports zero vulnerabilities; build:lib and lint pass. The affected-test run passed 2,932 tests with five skips and 13 shell/temp-directory setup failures. All 13 failures passed on the targeted rerun using Git Bash and a disposable D: temp directory (33 pass, one skip). MCP/capability tests passed 496 tests; custom lint-rule tests passed 247 with one skip. The c8 integration smoke passed nine MCP tests. Fallow 3.38.1 executes and reports a verified binary signature.

This is a source repair candidate. No release, production deployment, merge or PR closure was performed. GitHub's default-branch Dependabot alerts are separate from this candidate's audit result.
