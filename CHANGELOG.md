### What's changed in v0.1.0

* feat: initial commit (by @patrickleet)

* chore(deps): update unbounded-tech/workflow-simple-release action to v2.1.1 (#2) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat(deps): update helm release external-secrets to v0.20.4 (#1) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* chore(deps): update unbounded-tech/workflows-crossplane action to v2.13.0 (#4) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat(deps): update helm release external-secrets to v1 (#5) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat: helm chart xrd (by @patrickleet)

* chore(deps): update unbounded-tech/workflow-vnext-tag action to v1.21.0 (#7) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* feat(deps): update crossplane-contrib/provider-helm docker tag to v1.0.6 (#6) (by @renovate[bot])

  Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com>

* fix: remove hardcoded serviceMonitor from external-secrets (by @patrickleet)

  The serviceMonitor.enabled: true was causing e2e test failures because
  the test cluster doesn't have Prometheus Operator installed. Users who
  want ServiceMonitor can enable it via the values pass-through.

  Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>

* fix: add cluster-admin RBAC for e2e test (by @patrickleet)

  The Helm provider needs permissions to create namespaces when installing
  charts. Add ClusterRoleBinding granting cluster-admin to crossplane-system
  service accounts, matching the cert-manager e2e test pattern.

  Also align with cert-manager on autoUpgrade.channel and cleanup timeout.

  Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>


