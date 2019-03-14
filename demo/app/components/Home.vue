<template>
    <Page class="page">
        <ActionBar class="action-bar">
            <Label class="action-bar-title" text="Home"></Label>
        </ActionBar>

        <StackLayout>
            <Label class="info" horizontalAlignment="center" verticalAlignment="center">
                <FormattedString>
                    <Span :text="'==========' + this.features"/>
                </FormattedString>
            </Label>
                <Wikitude url="~/wikitude/index.html"
                    :features="features"
                    @WorldLoadSuccess="worldLoadSuccess"
                    @JSONReceived="jsonReceived"
                />
            <Label class="info" horizontalAlignment="center" verticalAlignment="center">
                <FormattedString>
                    <Span text="++++++++"/>
                </FormattedString>
            </Label>
        </StackLayout>
    </Page>
</template>

<script>
    import { Wikitude, Features } from 'nativescript-wikitude';

    export default {
        computed: {
            message() {
                return "Blank {N}-Vue app";
            }
        },
        data() {
            return {
                features: 64 | 1
            };
        },
        methods: {
            worldLoadSuccess(args) {
            },
            jsonReceived(data) {
            }
        }
    };
</script>

<style scoped lang="scss">
    // Start custom common variables
    @import '../app-variables';
    // End custom common variables

    // Custom styles
    .fa {
        color: $accent-dark;
    }

    .info {
        font-size: 20;
    }
</style>
