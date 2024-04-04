# SBOM to DependencyTrack

# Introduction

This GitHub action requires a previously created and valid CycloneDX JSON Software Bill-of-Materials (SBOM) as input. It will pull the current SBOM (inventory and vulnerabilities) from your OWASP Dependency-Track instance, merge the two and upload the aggregate of all project dependencies back to DTrack.

You need to already have created the SBOM you wish to upload, e.g. with cdxgen, syft, trivy, etc.

## Inputs

1) Dependency-Track url - required
2) Dependency-Track api-key - required
3) Project Name - required
4) Project Version - required
5) SBOM path/to/cyclonedx.sbom.json - required

## Output
The default token output confirms that the SBOM has been successfully uploaded to Dependency-Track.

## Usage

1) Navigate to your GitHub project directory.
2) Create a new file named .github/workflows/file-name.yaml.
3) Copy the provided code snippet below and paste it into the newly created YAML file.

### Use below snippet
```
      - name: SBOM-to-DependencyTrack
        uses: Drahtzieher/SBOM-to-DependencyTrack@0.0.1
        with:
          dt-url: <your dt url>
          # you can store api-key obtained in your github secrets.
          api-key: ${{ secrets.DTrackApiKey }}
          project-name: <your project name>
          project-version: <your project version >
          path-to-sbom: <path to your sbom file>
```

## Contribution

Suggestions are welcome!
