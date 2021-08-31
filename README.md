# Get Latest Container Tag and Next Version

[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Get%20Docker%20Hub%20Tag-blue.svg?colorA=24292e&colorB=0366d6&style=flat&longCache=true&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAOCAYAAAAfSC3RAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAAM6wAADOsB5dZE0gAAABl0RVh0U29mdHdhcmUAd3d3Lmlua3NjYXBlLm9yZ5vuPBoAAAERSURBVCiRhZG/SsMxFEZPfsVJ61jbxaF0cRQRcRJ9hlYn30IHN/+9iquDCOIsblIrOjqKgy5aKoJQj4O3EEtbPwhJbr6Te28CmdSKeqzeqr0YbfVIrTBKakvtOl5dtTkK+v4HfA9PEyBFCY9AGVgCBLaBp1jPAyfAJ/AAdIEG0dNAiyP7+K1qIfMdonZic6+WJoBJvQlvuwDqcXadUuqPA1NKAlexbRTAIMvMOCjTbMwl1LtI/6KWJ5Q6rT6Ht1MA58AX8Apcqqt5r2qhrgAXQC3CZ6i1+KMd9TRu3MvA3aH/fFPnBodb6oe6HM8+lYHrGdRXW8M9bMZtPXUji69lmf5Cmamq7quNLFZXD9Rq7v0Bpc1o/tp0fisAAAAASUVORK5CYII=)](https://github.com/marketplace/actions/get-container-image-tag)

Get the latest tag for an image on Docker Hub.

## Usage

Add following step to the end of your workflow:

```yaml
    - name: Get latest tag
      id: latest_tag
      uses: davidspek/gha-get-docker-hub-tags@0.1.5
      with:
        img: 'docker.io/mysql/mysql-server'  # container image to list tags from

    # Optionally check the tag we got back
    - name: Check outputs
      run: |
        echo "Latest Image Tag - ${{ steps.latest_tag.outputs.latest_tag }}"
        echo "Next Major Tag - ${{ steps.latest_tag.outputs.new_major }}"
        echo "Next Minor Tag - ${{ steps.latest_tag.outputs.new_minor }}"
        echo "Next Patch Tag - ${{ steps.latest_tag.outputs.new_patch }}"
        echo "Next Major Tag with v prefix - ${{ steps.latest_tag.outputs.new_v_major }}"
        echo "Next Minor Tag with v prefix - ${{ steps.latest_tag.outputs.new_v_minor }}"
        echo "Next Patch Tag with v prefix - ${{ steps.latest_tag.outputs.new_v_patch }}"
```
